# Zed Attack Proxy (ZAP) 

1. **Purpose and Flexibility**:  
   - ZAP is a **free, open-source tool** for penetration testing, specifically designed for **web application security** testing.
   - It’s **flexible and extensible**, meaning it can be customized with additional functionality and adapted to different testing needs.

2. **Manipulator-in-the-Middle Proxy**:  
   - ZAP functions as a **manipulator-in-the-middle proxy** by positioning itself between a tester’s browser and the web application.
   - This allows ZAP to **intercept, inspect, and modify messages** exchanged between the browser and web app, offering a controlled testing environment.

3. **Stand-alone and Daemon Modes**:  
   - ZAP can operate as a **stand-alone application** or as a **daemon** process, making it adaptable to various use cases.

4. **Corporate Proxy Compatibility**:  
   - In environments with existing network proxies, like corporate networks, **ZAP can be configured to work with an existing proxy**.

5. **User Accessibility and Add-ons**:  
   - ZAP is designed for a range of users, from **newcomers to security testing to experienced specialists**.
   - It’s available for **major OS platforms and Docker**, allowing flexibility across different systems.
   - The **ZAP Marketplace** within the client provides access to additional **free add-ons** to extend functionality as needed.

6. **Open-Source Community Contribution**:  
   - As an **open-source project**, ZAP allows users to inspect its code, contribute to development, fix bugs, and add new features.
   - Users can also author specialized add-ons, which are helpful for unique testing scenarios.

Zap is as similar to Brup suite

Advantages OWASP ZAP has over Burp Suite in terms of features:

1. **Automated Web Application Scan**: 
   - **OWASP ZAP** offers an automated scan feature to detect vulnerabilities by passively and actively scanning a web application, building a sitemap, and identifying security issues. 
   - **Burp Suite** also provides these capabilities but only in the paid version, whereas ZAP offers it for free.

2. **Web Spidering**:
   - **OWASP ZAP** includes a web spidering feature, which passively builds a map of the website by “crawling” or exploring its pages. This process helps identify all accessible endpoints, links, and resources in a web application, aiding in understanding and testing it more thoroughly.
   - In **Burp Suite**, web spidering is available only in the paid version.

3. **Unthrottled Intruder**:
   - With **OWASP ZAP**, you can brute force attempts on login pages or other areas that require specific input (e.g., password fields). This feature allows the tool to perform these brute-force attacks at the maximum speed your system and the target server can handle, unrestricted by any artificial limits.
   - In **Burp Suite**, this capability is restricted to the paid version and may have throttling or other limitations.

4. **Integrated Interception and Browsing**:
   - **OWASP ZAP** simplifies the process of manual testing by letting you intercept and manipulate requests directly within the browsing environment. With ZAP, you can browse normally, and ZAP will automatically intercept traffic, avoiding the need to switch windows constantly.
   - In **Burp Suite**, each request needs to be manually forwarded, which can slow down the process and make it more tedious.

Overall, OWASP ZAP provides a range of features for free that are available only in Burp Suite’s paid version, making it a highly accessible tool for web application security testing.

You can also learn more from [Try Hack Me ](https://tryhackme.com/r/room/learnowaspzap) room.


When using **OWASP ZAP** (Zed Attack Proxy) to scan a website, the **automated scan** feature offers options for both **traditional spider** and **Ajax spider** modes. Here’s an overview of each, along with setup instructions:

### Automated Scan Overview
- **Passive and Active Scanning**: ZAP's automated scan performs both passive scans (less intrusive, focusing on building a sitemap) and active scans (which try to detect vulnerabilities by testing for issues directly).
- **Sitemap Building**: The automated scan maps out the website's structure by discovering links, directories, and hidden content, helping you understand the application and potential weak spots.

### Spider Options

1. **Traditional Spider**:
   - **Function**: This is a passive scan that enumerates links and directories without brute-forcing hidden resources.
   - **Usage**: The traditional spider is relatively quiet compared to brute-force techniques, and it’s often used for initial scans. It may not find every resource, but it’s effective for quickly mapping accessible areas like login pages or other key sections.

2. **Ajax Spider**:
   - **Function**: The Ajax spider is an add-on that crawls JavaScript-heavy (AJAX) sites more thoroughly, covering interactive and dynamic content that traditional spiders may miss.
   - **Usage**: The Ajax Spider integrates **Crawljax**, which interacts with AJAX-driven components, simulating user actions and uncovering hidden elements on dynamic pages.
   - **Browser Requirement**: The Ajax Spider requires a web browser and proxy setup, which makes it compatible with **HTMLUnit**—a headless browser that supports JavaScript.

### Setting up HTMLUnit for the Ajax Spider

1. **Install HTMLUnit**:
   - Run the following command to install the HTMLUnit library, which ZAP will use to simulate a browser:
     ```bash
     sudo apt install libjenkins-htmlunit-core-js-java
     ```

2. **Select HTMLUnit in ZAP**:
   - In ZAP, go to the **Ajax Spider** settings and choose **HTMLUnit** from the dropdown menu.

3. **Configure Options**:
   - Access further configuration by opening the **Options** menu (shortcut `Ctrl + Alt + O`), where you can set up parameters for both the traditional and Ajax spiders for customized scans.

### Running the Automated Scan
- Once configured, run the automated scan by selecting either or both spiders. Using both the traditional spider and Ajax spider together provides a comprehensive sitemap, covering both static and dynamic content.

## Installation
1. Download the appropriate installer from the Zaproxy.org

2. Open your terminal and change it to root user with command: 
` sudo su `

3. ` cd Downloads/`

4. ` chmod +x name_of_the_file ` to change file into executable permission.

5. ` ./name_of_the_file ` to install.

And if you get **Failed to load module "canberra-gtk-module"** issues, run the command ` sudo apt install libcanberra-gtk-module libcanberra-gtk3-module `.


 