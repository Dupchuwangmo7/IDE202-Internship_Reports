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


## 3. OpenVAS
 It is vulnerability analysis tool that allows  scan network devices and server. It looks for an IP address and checks for any open service by scanning through the open ports, vulnerabilities and misconfigation in the existing facilities.


It is a full-featured vulnerability scanner which include unauthenticated and authenticated testing.

## 4. Nexpose
Nexpose vulnerability scanner is an automated penetration testing system. Nexpose can help you identify the open ports, applications, and services on each scanned machine.

- It is one of the most leading and the most used Network vulnerability scanner.
- And it operates all physical location, cloud and mobile environment.
-  Nexpose has a desirable feature called Live Monitoring. Live Monitoring collects data and creates action plans.

 ## 5. Necess
 - It takes care of malware, software issues, patching and misconfigation adware removal tool over a wide range of application and operating systems.

 - It is ideal tool for pen tester, ethical hacker and bug hunters.

 - Necess springs and procative security procedure by identifying the vulnerabilities in time before hacker use it for malicious purpose.

 - It takes care of remote code execuation flaws.
 
 - it works on the most of the network devices including physical,virtual and cloud infrastructure. 

 ## 6. Nikto
 - It is a vulnerability scanner that helps in understanding server versions, functions perdorming a test on the websers to identify threads and walware presences.

 - It can also scan the different protocols like HTTP, https, httpd and more.
 
 - It also provides cookies, proxy and SSL support.

- It is preferred for its efficiency and server hardening capabilities.

Installation - ` sudo apt-get install nikto -y `

![alt text](<Images/Screenshot from 2024-09-23 22-56-04.png>)

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
