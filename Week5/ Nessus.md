# Nessus 
**Nessus** is a widely used vulnerability assessment tool that helps in identifying, analyzing, and managing security vulnerabilities in networks, applications, and various systems. Developed by Tenable, Nessus is known for its reliability, ease of use, and a broad range of supported systems. It’s widely used by security professionals and organizations to find and fix security vulnerabilities before attackers can exploit them.

### Key Features of Nessus
1. **Vulnerability Scanning**:
   - Nessus can scan for thousands of vulnerabilities across various systems, including servers, databases, firewalls, virtual environments, and even cloud infrastructures. It identifies common vulnerabilities such as misconfigurations, missing patches, and software flaws.

2. **Extensive Plugin Library**:
   - Nessus uses a large library of plugins, updated regularly by Tenable, to identify the latest vulnerabilities. These plugins can detect various issues, including outdated software, known security flaws, and configuration weaknesses.

3. **Comprehensive Reporting**:
   - Nessus generates detailed, customizable reports that can help prioritize vulnerabilities based on severity. This helps in efficiently addressing critical issues and managing risk within an organization.

4. **Compliance Checks**:
   - It can perform compliance checks against industry standards such as PCI-DSS, HIPAA, and NIST, ensuring that systems meet required security and data protection standards.

5. **Policy Auditing**:
   - Nessus can assess configurations against a defined security policy, helping ensure that systems remain within organizational compliance guidelines.

### Types of Nessus Scans
- **Network Scanning**: Scans entire network subnets for open ports, services, and other indicators of vulnerabilities.
- **Credentialed vs. Non-Credentialed Scans**: Credentialed scans use system access credentials for a deeper analysis, while non-credentialed scans are less intrusive and can detect surface-level vulnerabilities.
- **Web Application Scanning**: Finds vulnerabilities in web applications, such as SQL injection and cross-site scripting (XSS).
- **Compliance Scanning**: Checks systems against specific compliance and configuration standards.
- **Cloud and Virtual Environment Scanning**: Identifies vulnerabilities in cloud infrastructure and virtual environments (e.g., AWS, Azure).

### Use Cases
- **Penetration Testing**: Nessus helps identify weaknesses that can be exploited in penetration tests.
- **Vulnerability Management**: Automates the process of scanning and tracking vulnerabilities, making it easier to maintain a secure environment.
- **Compliance Audits**: Provides support for regulatory and organizational compliance through thorough vulnerability assessments and configuration checks.

### Nessus Editions
1. **Nessus Essentials**: Free version with basic vulnerability scanning capabilities.
2. **Nessus Professional**: Paid version with advanced features, including unlimited IP scanning and in-depth vulnerability assessment capabilities for enterprises.
3. **Nessus Manager**: Centralized management solution that integrates with Tenable’s broader product ecosystem.

Nessus is widely adopted because of its comprehensive scanning capabilities, ease of use, and regular updates. It’s often paired with other security tools in a larger vulnerability management framework to help organizations stay proactive against security threats.

## Installation
1. Download the latest version of Nessus from [here](https://www.tenable.com/downloads/nessus?loginAttempted=true) 

2. Open your terminal and change it to root user with command: 
` sudo su `

3. Run the command ` dpkg -i file_name `

![alt text](<Images/Screenshot from 2024-10-16 21-51-34.png>)

4. Run the ` /bin/systemctl start nessusd.service ` command

5. Go to https://localhost:8834/ 
which is default port for the nessus.

![alt text](<Images/Screenshot from 2024-10-16 21-54-56.png>)

6. Click on Advance **Advanced** and click on continue.

7. Rigester for **Register for Nessus Essentials**.

## How to use nessus


### Step 1: Configure and Customize Scans
1. **Log in to the Nessus Console**: Access the web interface at `https://localhost:8834` or at the specific IP and port where it’s hosted.
2. **Create a New Scan**:
   - Go to the **Scans** tab and click **New Scan**.
   - Choose a **Scan Template** based on your goals. Common templates include:
     - **Basic Network Scan** for general vulnerability scanning.
     - **Advanced Scan** for more control over scan options.
     - **Web Application Tests** for web vulnerabilities like SQL injection or XSS.
     - **Compliance Audit** to check compliance with specific standards.
3. **Configure the Scan Settings**:
   - **Name the Scan**: Give it a descriptive name.
   - **Target**: Enter the IP address, range, or hostname of the target system.
   - **Credentials (Optional)**: For a more in-depth analysis, add credentials (username and password) to access the system. This is called a **credentialed scan** and allows Nessus to check configuration settings and perform deeper scans.

### Step 2: Run the Scan
1. **Start the Scan**: Click **Save** to save the scan configuration, then click **Launch** to begin scanning.
2. **Monitor Scan Progress**: The dashboard shows real-time progress, including the number of detected vulnerabilities. Scans may take some time, depending on the complexity and size of the target environment.

### Step 3: Review and Analyze Scan Results
1. **View Scan Results**: Once completed, click on the scan name to see the results.
2. **Examine Vulnerabilities**:
   - **Severity Levels**: Vulnerabilities are categorized by severity—**Critical**, **High**, **Medium**, and **Low**.
   - **Detailed Descriptions**: Each finding includes a description, affected software/hardware, and potential impacts.
   - **Remediation Guidance**: Nessus offers remediation steps, helping you understand how to fix or mitigate each vulnerability.
3. **Export Results**: Nessus allows you to export reports in various formats (e.g., HTML, PDF, CSV) for easier analysis, record-keeping, or sharing with teams.

### Step 4: Remediate and Rescan
1. **Remediate Identified Vulnerabilities**: Based on Nessus’s recommendations, update software, fix misconfigurations, or apply patches.
2. **Rescan**: After remediating vulnerabilities, run a follow-up scan to verify that the issues have been resolved.

### Tips for Effective Nessus Use
- **Run Regular Scans**: Schedule periodic scans to stay on top of new vulnerabilities.
- **Use Plugin Updates**: Regularly update Nessus’s plugins to detect the latest vulnerabilities.
- **Leverage Compliance Templates**: For regulatory requirements (e.g., PCI-DSS, HIPAA), use Nessus’s compliance templates to ensure alignment with standards.

### Security Considerations
- **Limit Access**: Secure the Nessus console and limit access to authorized users only.
- **Be Cautious with Credentialed Scans**: Ensure credentials are managed securely, as they provide Nessus with deeper system access.
  



