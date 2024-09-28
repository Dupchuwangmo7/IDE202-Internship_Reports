# Vulnerabilities Scanners

They are valuable tools that search for and report on vulnerabilities that are present in an IT infrastructure. These scans can give an organization an idea of what security threats they may be facing by giving insights into potential security waeknesses present in their environment.

And vulnerabilities scanning is the automatic way to protect website or web application from malicious hacker attacks. 

There are multiple vulnerability scanner to ensure safety of an environment.

#### List of Vulnerabilities Scanner

## 1. Acunetix
It is an automated web applicaton security testing tools that audits web applications by checking for vulnerabilities like SQL injections, Cross site scripting and other exploitable vulnerabilities.

 Acunetix scans any website or web application that is accessible via a web browser and uses the HTTP/HTTPS protocol.

#### How is works?
1. Acunetix DeepScan analyses the entire website by following all the links on the site, including links that are dynamically constructed using JavaScript, and links found in robots.txt and sitemap.xml (if available).

2. If Acunetix AcuSensor Technology is enabled, the sensor will retrieve a listing of all the files present in the web application directory and add the files not found by the crawler to the crawler output. Such files usually are not discovered by the crawler as they are not accessible from the web server, or not linked through the website.
-  Acunetix AcuSensor also analyses files which are not accessible from the internet, such as web.config.

###### note 
A web crawler, or spider, is a type of bot that is typically operated by search engines. 

3. After the crawling process, the scanner automatically launches a series of vulnerability checks on each page found, in essence emulating a hacker. Acunetix also analyses each page for places where it can input data, and subsequently attempts all the different input combinations. This is the Automated Scan Stage. If the AcuSensor Technology is enabled, a series of additional vulnerability checks are launched against the website. More information about AcuSensor is provided in the following section.

4. The vulnerabilities identified are shown in the Scan Results. Each vulnerability alert contains information about the vulnerability such as POST data used, affected item, HTTP response of the server and more.

5. If AcuSensor Technology is used, details such as source code line number, stack trace or affected SQL query which lead to the vulnerability are listed.  Recommendations on how to fix the vulnerability are also shown.

6. Various reports can be generated on completed scans, including Executive Summary report, Developer report and various compliance reports.


#### What is Acunetix deepscan?

- Is the latest revolutionary technology avaliable within acunetix that can crawl and scan modern     HTML5 and JavaScript-based web applications.

- Only web vulnerabilities scanner on the market capable of doing this.

#### What is AcuSensor Technology?
-  it identifies more vulnerabilities than other Web Application Scanners, whilst generating less false positives.

- Acunetix AcuSensor indicates exactly where in code the vulnerability is and reports additional debug information.

- Alerts about the web application configuration problems which can result in a security misconfiguration, or expose sensitive information. 



## 2. Burp Suite
It is a web vulnerability scanner that is frequently updated, and integrates with bug tracking systems.

![alt text](<Images/Screenshot from 2024-09-23 17-26-46.png>)

The tools offered by BurpSuite are:

1. Spider:
- It is a web spider/crawler that is used to map the target web application. The objective of the mapping is to get a list of endpoints so that their functionality can be observed and potential vulnerabilities can be found. 

2. Proxy:
- BurpSuite contains an intercepting proxy that lets the user see and modify the contents of requests and responses while they are in transit.

3. Intruder:

The intruder is used for:

- Brute-force attacks on password forms, pin forms, and other such forms.
- The dictionary attack on password forms, fields that are suspected of being vulnerable to XSS or SQL injection.
- Testing and attacking rate limiting on the web-app.

4. Repeater:
Repeater lets a user send requests repeatedly with manual modifications. It is used for:

- Verifying whether the user-supplied values are being verified.
- If user-supplied values are being verified, how well is it being done?
- What values is the server expecting in an input parameter/request header?
How does the server handle unexpected values?
- Is input sanitation being applied by the server?
- How well the server sanitizes the user-supplied inputs?
- What is the sanitation style being used by the server?
- Among all the cookies present, which one is the actual session cookie.

References - GeeksforGeeks. (2022, September 30). What is Burp Suite? GeeksforGeeks.

## 3. OpenVAS
 It is vulnerability analysis tool that allows  scan network devices and server. It looks for an IP address and checks for any open service by scanning through the open ports, vulnerabilities and misconfigation in the existing facilities.

It is a full-featured vulnerability scanner which include unauthenticated and authenticated testing.

#### OpenVAS offers
1. Simple scan

- The OpenVAS web interface includes a wizard to help set up scans of target machines.
- Here, we need to give IP address to scan.
- As the scan runs, any vulnerabilities that it detects will be listed in the report.

2. Advance scan 
- the OpenVAS web interface also includes an Advanced Task Wizard 
- The advanced wizard offers the following scanning options:

  - Setting a name for the task
  - Choosing a scan config
  - Setting the target IP address
  - Scheduling future scans
   - Using a credentialed scan

## 4. Nexpose
Nexpose vulnerability scanner is an automated penetration testing system. Nexpose can help you identify the open ports, applications, and services on each scanned machine.

#### Integrating Nexpose with Metasploit

The Nexpose vulnerability scanner integrates with Rapid7’s Metasploit to then support vulnerability assessment and validation. 


#### Why Nexpose?
- It is one of the most leading and the most used Network vulnerability scanner.
- And it operates all physical location, cloud and mobile environment.
-  Nexpose has a desirable feature called Live Monitoring. Live Monitoring collects data and creates action plans.
- It aslo have feature called Live board. Live boards visual reporting is constantly updated in real time to provide much better visibile
- remediation workflow, which  tracks and manages the security team’s operations and monitors the overall progress of the team in addressing the identified vulnerabilities.

Vulnerabilities that are exploited are first prioritized by Nexpose. This keeps security operations teams from getting overloaded with security alerts. 

 ## 5. Nessus
 - It takes care of malware, software issues, patching and misconfigation adware removal tool over a wide range of application and operating systems.

 - It is ideal tool for pen tester, ethical hacker and bug hunters.

 - Nessus springs and procative security procedure by identifying the vulnerabilities in time before hacker use it for malicious purpose.

 - It takes care of remote code execuation flaws.
 
 - it works on the most of the network devices including physical,virtual and cloud infrastructure. 

 #### How Nessus Scans Work
Tenable and the Nessus team continually develop “plugins” to perform specific actions such as identifying new vulnerabilities.

1. When a vulnerability scan is run, Nessus will attempt to establish a connection to  network devices and run through its plugins to identify the type of device, the operating system, any running services, the specific versions of these services, and other useful information.

2. As more information is gathered, vulnerability detection tests are also run to determine what security weaknesses devices are affected by, what updates may be missing, and what known vulnerabilities  devices are impacted by.

3. This information is presented within a user interface and can be configured to run on a set schedule and provide email notifications when completed.

References - Lugsden, A. (2024, August 29). What is Nessus: Running Your First Vulnerability Scan. Forge Secure.

 ## 6. Nikto
 - It is a vulnerability scanner that helps in understanding server versions, functions perdorming a test on the websers to identify threads and walware presences.

 - It can also scan the different protocols like HTTP, https, httpd and more.
 
 - It also provides cookies, proxy and SSL support.

- It is preferred for its efficiency and server hardening capabilities.

Installation - ` sudo apt-get install nikto -y `

![alt text](<Images/Screenshot from 2024-09-23 22-56-04.png>)

#### Nikto commands to perform vulnerability scanning

1. ¶Running a basic website scan

- The most basic way to scan a host with Nikto is to use the -h flag with the nikto command:

` nikto -h example.com` 

![alt text](<Images/Screenshot from 2024-09-24 22-49-44.png>)

2. Running a scan on a website with SSL

- Nikto also has an SSL scanner mode, for SSL certificates installed on a website. With this we can get SSL cipher and issuer information.

` nikto -h example.com -ssl`

3. Scanning specific ports with Nikto
- On certain deployments, web servers are run on non-standard ports like 8081 or 8080, or multiple web servers are run on the same host on different network ports. It's therefore vital to have the ability to scan specific ports as well as the main 80 and 443 ports.
` nikto -h example.com -port 8083`

4. Save Nikto output to a specific file
- The Nikto scanner also includes the ability to save the scan output to a file for future reference. This is ideal when running multiple scans and/or large scans which can be easier to reference from a file.

` nikto -h example.com -output /path/to/file.name`

5. Scanning websites which require authentication
- Nikto also includes the ability to scan websites which are protected by http authentication:

` nikto -h example.com -id username:password`

6. Scanning through a network proxy
- Certain websites may only be available through a network proxy or specific IP, and this feature allows Nikto to scan the website through that proxy address as well:

` nikto -h example.com -useproxy proxy.ip.address`

## 7.Nmap

It is security scanner that is also used by organizations for network discovery, inventory, managing service upgrade schedules, and monitoring host or service uptime.

Nmap uses raw IP packets in novel ways to determine what hosts are available on the network, what services (application name and version) those hosts are offering, what operating systems (and OS versions) they are running, what type of packet filters/firewalls are in use, and dozens of other characteristics.

Nmap is
- Flexible 
- Powerful
- Portable
- Easy
- free
- Well Documented

#### Nmap Commands
1. Basic scans
- Scanning the list of active devices on a network is the first step in network mapping. There are two types of scans you can use for that:
  - Ping scan — Scans the list of devices up and running on a given subnet.
    - command : ` nmap -sp ip.address`
  - Scan a single host — Scans a single host for 1000 well-known ports. These ports are the ones used by popular services like SQL, SNTP, apache, and others.
     - command : `nmap scanme.nmap.org`

     ![alt text](<Images/Screenshot from 2024-09-24 22-57-02.png>)

2. Stealth scan
- Stealth scanning is performed by sending an SYN packet and analyzing the response.

command : `nmap -sS scanme.nmap.org`

3. Version scanning
-  application versions is a crucial part in penetration testing.

command : `nmap -sV scanme.nmap.org`

4. OS Scanning
- Nmap can also provide information about the underlying operating system using TCP/IP fingerprinting.

# References
Lugsden, A. (2024, August 29). What is Nessus: Running Your First Vulnerability Scan. Forge Secure.