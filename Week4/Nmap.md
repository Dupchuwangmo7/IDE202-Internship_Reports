# Nmap

Computers use "ports" to communicate. Each service (like a web server) runs on a specific port, which acts like a door for data to come in and out. For example, web traffic uses port 80 for HTTP and port 443 for HTTPS. These are called “standard” ports because they’re commonly used for the same types of services across the internet.

The first stage of this mapping is called port scanning.Nmap is the go-to tool for port scanning because of its flexibility and power. It’s widely used in the industry and even comes with a scripting engine to help automate vulnerability scans and, in some cases, even perform basic exploits.

We can view a list of all available switches with two commands:
  - `nmap -h` for the help menu.
  - `man nmap` to access the full manual page, providing detailed information about each option.

![alt text](<Images/Screenshot from 2024-10-08 12-23-52.png>)

### The main types of Nmap scans 

1. **Basic Port Scans**  
   These are the three most common scan types in Nmap:
   - **TCP Connect Scan (`-sT`)**: This scan completes a full connection with the target system on each port. It’s reliable but can be easily detected by firewalls and Intrusion Detection Systems (IDS).
   - **SYN Scan (`-sS`)**: Also called a "Half-open" scan, it sends a SYN packet to each port but doesn’t complete the connection. This is faster and less detectable than a TCP Connect Scan, making it the preferred option for stealthy scanning.
   - **UDP Scan (`-sU`)**: This scan checks for open UDP ports, as some services (e.g., DNS or SNMP) don’t use TCP. UDP scanning is generally slower than TCP scans since UDP has no built-in handshake to confirm connections.

2. **Less Common Scan Types**  
   These scans are less commonly used but can be helpful for bypassing firewalls or IDS:
   - **TCP Null Scan (`-sN`)**: This scan sends packets with no flags set. It can sometimes bypass firewalls or systems expecting standard scan types.
   - **TCP FIN Scan (`-sF`)**: Sends a FIN (finish) flag to the target. Some systems may not log or respond to FIN scans, making them stealthier.
   - **TCP Xmas Scan (`-sX`)**: Sends packets with multiple flags (FIN, PSH, URG). Like the Null and FIN scans, it can slip past certain firewalls and IDS because of its unusual packet structure.
