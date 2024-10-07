# Introductory Networking

#### Open Systems Interconnection(OSI)
It is a standardised model which is used to demostrate the theory behind computer networking.

The OSI model consists of seven layers:

- Layer 7 Application
- Layer 6 Presentation
- Layer 5 Session 
- Layer 4 Transport
- Layer 3 Network 
- Layer 2 Data link
-  Layer 1 Physical

## Layer 7 Application
This layer controls the input and output of data and provides the application functions.

## Layer 6 Presentation
The presentation layer translates the data into a standardised format, as well as handling any encryption, compression or other transformations to the data

##  Layer 5 Session
The session layer controls the logical connection between two systems and prevents, for example, connection breakdowns or other problems.

## Layer 4 Transport
 Its first purpose is to choose the protocol over which the data is to be transmitted. 

 The two most common protocols in the transport layer are TCP (Transmission Control Protocol) and UDP (User Datagram Protocol); 
 - **TCP** - connection-based transmission and  reliable transmission.

- **UDP** - it is not connection based as packets of data are essentially thrown at he receving computer. 

## Layer 3 Network 
The network layer is responsible for locating the destination of your request.
Data is transmitted over the entire network from the sender to the receiver.

## Layer 2 Data link
The central task of layer 2 is to enable reliable and error-free transmissions on the respective medium. 

## Layer 1 Physical
When data is transferred over a network, it doesn't travel as readable text or images—it’s transformed into these signals that can travel physically between devices. The physical layer is responsible for making sure these signals move reliably from one device to another, ensuring that the devices are connected and can communicate.

# Encapsulation

1. **Encapsulation**: When a computer sends data, it starts at the top layer (Application) and moves down each layer in the OSI model. At each step, the data gets wrapped (or "encapsulated") with additional information that helps it travel across the network.
   
2. **Changing Data Names**: As the data moves through the layers, it’s referred to by different names:
   - **Layers 7, 6, and 5 (Application, Presentation, and Session)**: The data is just called "data."
   - **Transport Layer (Layer 4)**: Here, it’s called a **segment** if using TCP (a reliable protocol) or a **datagram** if using UDP (a faster, less reliable protocol).
   - **Network Layer (Layer 3)**: Now it becomes a **packet**.
   - **Data Link Layer (Layer 2)**: The packet is turned into a **frame**.
   - **Physical Layer (Layer 1)**: Finally, the frame is broken down into **bits** (1s and 0s) to travel over the physical network.

3. **De-encapsulation**: When the receiving computer gets the bits, it reverses the process, stripping away each layer’s information as it moves upward. By the time it reaches the Application layer, the original data is fully restored.

4. **Standardization**: This method of encapsulation and de-encapsulation ensures that all devices can communicate, regardless of their type or brand. So, any network-enabled device can send a request to any other reachable device with confidence it will be understood.

# The TCP/IP Model

### TCP/IP Model Overview
The TCP/IP model, foundational in real-world networking, has four layers:

1. **Application Layer**: Where applications and protocols (like HTTP, FTP, etc.) work to handle user data.
2. **Transport Layer**: Manages data transfer between devices using either TCP (for reliable connections) or UDP (for faster, less reliable connections).
3. **Internet Layer**: Directs data packets across networks using the Internet Protocol (IP).
4. **Network Interface Layer**: Handles hardware-level operations to physically send data over the network.

While some modern sources split the Network Interface into **Data Link** and **Physical** layers, the original four-layer TCP/IP structure remains widely used.

### Comparison with the OSI Model
The TCP/IP model’s four layers cover the same functions as the OSI model’s seven layers but with fewer divisions:

- **TCP/IP Application Layer** = OSI Application, Presentation, and Session Layers.
- **TCP/IP Transport Layer** = OSI Transport Layer.
- **TCP/IP Internet Layer** = OSI Network Layer.
- **TCP/IP Network Interface Layer** = OSI Data Link and Physical Layers.

The OSI model isn’t used directly in networking but serves as an excellent learning tool because it breaks down networking functions in more detail.

### Encapsulation and De-encapsulation
Just like the OSI model, the TCP/IP model follows **encapsulation** (adding headers as data moves down the layers) and **de-encapsulation** (removing headers as data moves up the layers) to format data for transmission. Each layer’s header ensures data is handled properly when moving from one layer to the next.

### TCP and the Three-Way Handshake
TCP (Transmission Control Protocol) is crucial for reliable data transfer in the TCP/IP model. It establishes a secure, error-checked connection before data transmission through a process known as the **three-way handshake**:

1. **SYN (Synchronize)**: The client  sends a SYN packet to initiate the connection.
2. **SYN-ACK (Synchronize and Acknowledge)**: The server responds with both SYN and ACK packets, acknowledging the request.
3. **ACK (Acknowledge)**: The client sends an ACK packet, confirming the connection.

# Ping 
### Ping Command

- **Purpose**: The `ping` command tests the connectivity to a remote resource, such as a website or another computer on a network.
  
- **Protocol**: It uses the **ICMP (Internet Control Message Protocol)**, which operates at the Network layer of the OSI model and the Internet layer of the TCP/IP model. 

- **Basic Syntax**: The command format is:
  ```bash
  ping <target>
  ```
  For example, to ping Google, you would use:
  ```bash
  ping google.com
  ```


### What Happens When You Ping?
When we run the `ping` command:

1. **Sends Echo Requests**: Our computer sends ICMP Echo Request packets to the target.
2. **Receives Echo Replies**: If the target is reachable, it sends back ICMP Echo Reply packets.
3. **Displays Results**: The command shows the response time and other statistics, including the IP address of the target.

### Benefits of the Ping Command
- **Connectivity Testing**: It helps determine if a network connection is functioning.
- **IP Address Resolution**: It can resolve domain names to IP addresses, which is useful for troubleshooting.
- **Ubiquity**: It is supported across various operating systems and network-enabled devices.

### Using the Man Page

```bash
man ping
```
This will display detailed information about how to use the command, including options such as:

- `-c <count>`: Sends a specific number of packets.
- `-i <interval>`: Sets the interval between sending packets.
- `-t <ttl>`: Sets the Time to Live (TTL) for packets.

![alt text](<Images/Screenshot from 2024-10-07 21-44-37.png>)


# Traceroute
A traceroute provides a map of how data on the internet travels from its source to its destination.

### What is Traceroute?
- **Purpose**: Traceroute maps out the specific route that packets take to reach a destination. This helps diagnose where delays or issues might be occurring on the network path.
  
- **Intermediate Stops**: When a request is sent over the internet, it often passes through multiple intermediate routers or servers, known as **hops**. Traceroute shows each hop and provides response times for each one, helping you identify any lagging points.

### Syntax and Usage

On Linux, the basic syntax for traceroute is:
```bash
traceroute <destination>
```

### Key Details
1. **Hops and IP Addresses**: Each line in the output represents a hop, showing the IP address (or hostname if resolvable) and response time for each router it passes through.
2. **Protocol**: On Windows, the `tracert` command uses **ICMP**, the same protocol used by `ping`. On Linux, however, `traceroute` uses **UDP** by default, but this can be changed with options.
3. **TTL (Time To Live)**: Traceroute works by setting a low TTL (Time to Live) value on packets and increasing it with each hop. Each router that receives the packet decreases the TTL by one and responds with an error if TTL hits zero. This helps identify each router along the path.

### Useful Switches
The `man traceroute` command can provide details on available switches, but here are some useful ones:

- `-I`: Use ICMP (similar to Windows `tracert` behavior).
- `-p <port>`: Specify the port to use with UDP packets.
- `-q <n>`: Set the number of queries per hop. The default is 3.

![alt text](<Images/Screenshot from 2024-10-07 22-15-27.png>)

#  WHOIS
**Domain Names** play a crucial role in making the internet user-friendly by letting us use recognizable addresses instead of IP addresses.

### What is a Domain Name?
- **Function**: A domain name is a human-readable label that translates into an IP address (e.g., `tryhackme.com` instead of its numerical IP).

### Whois Command 
**Whois** is a tool that queries the database of registered domains to retrieve information about the owner, registrar, and registration details of a domain.

- **Installing Whois**: We can install it on Debian-based systems with:
  ```bash
  sudo apt update && sudo apt-get install whois
  ```

- **Syntax**: The basic command to perform a lookup is:
  ```bash
  whois <domain>
  ```


### Information You Can Find with Whois
- **Domain Name and Registrar**: The name of the domain and the company that registered it.
- **Registration Dates**: The last renewal date and when the lease is set to expire.
- **Nameservers**: The servers responsible for handling requests for the domain.
- **Registrant Information**: Contact information about the domain owner (though in Europe, personal details are often redacted for privacy under GDPR).

### Practical Application
Whois can help identify the organization behind a domain, check registration and expiry dates, and, in some cases, gather contact information. This is useful for security assessments, verifying domain ownership, and troubleshooting network issues.

# Dig 
The **Domain Name System (DNS)** is essential for converting user-friendly domain names into IP addresses that computers can understand. 

### How DNS Works: 

1. **Hosts File Check**:
   - When we type a domain in our browser,our computer first checks its **hosts file**. This file can have manually mapped domain-to-IP entries, although it’s not commonly used in modern systems.

2. **Local DNS Cache Check**:
   - If there’s no entry in the hosts file, our computer checks its **local DNS cache**. This cache stores IP addresses from previous queries, allowing faster access if we’ve recently visited the site.

3. **Querying the Recursive DNS Server**:
   - If the domain is not found in the local cache, our computer sends a query to a **recursive DNS server**, usually maintained by our ISP or a public provider like Google (8.8.8.8) or OpenDNS. This server may have the IP cached, and if so, it responds with the answer.

4. **Root Name Server**:
   - If the recursive DNS server doesn’t have the IP, it queries a **root name server**. The root servers direct the query based on the domain extension (e.g., `.com`, `.org`).

5. **Top-Level Domain (TLD) Server**:
   - Next, the request goes to a **TLD server** associated with the domain’s extension. For example, a `.com` TLD server handles `.com` requests. This server knows where to find the **Authoritative Name Server**.

6. **Authoritative Name Server**:
   - The TLD server directs the request to the **authoritative name server**, which stores the specific domain’s DNS records. This server provides the requested IP address to the recursive DNS server, which in turn sends it back to our computer.

7. **Caching with TTL**:
   - Once our computer receives the IP address, it stores it in its local DNS cache for a period defined by **TTL** (Time To Live), which tells computer how long to keep the record before rechecking.

### Using the **dig** Command

**dig** is a command-line tool that lets perform DNS lookups manually.

- **Basic Syntax**: To query a domain using a specific DNS server:
  ```bash
  dig <domain> @<dns-server-ip>
  ```
  For example:
  ```bash
  dig google.com @8.8.8.8
  ```


### Why Use dig?
**dig** is invaluable for troubleshooting DNS issues, checking if DNS records have updated, or exploring DNS configurations.


