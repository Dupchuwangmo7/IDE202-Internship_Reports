

# SSH  

**Introduction**  
SSH, or Secure Shell, is a protocol that provides secure remote access, management, and file transfer over an unsecured network. By establishing an encrypted communication channel, SSH protects against eavesdropping, unauthorized access, and data tampering. It is a cornerstone technology for developers, system administrators, and IT professionals, enabling secure interactions with remote systems.  

---

**Architecture of SSH**  

SSH operates on a **client-server model**, where the client initiates a connection to the server. To ensure security and flexibility, SSH is designed with three distinct layers:  

1. **Transport Layer**  
   - Handles encryption, decryption, and compression of data.  
   - Ensures data integrity using cryptographic algorithms like AES and ChaCha20.  
   - Negotiates the encryption and key exchange protocols between client and server.  

2. **Authentication Layer**  
   - Verifies the client's identity using various methods, including:  
     - **Password-based authentication**: The simplest method, though less secure if used alone.  
     - **Public key authentication**: A more secure method that relies on cryptographic key pairs.  
     - **Certificate-based authentication**: Leverages digital certificates issued by trusted authorities.  
   - Prevents unauthorized access by authenticating both the client and server.

3. **Connection Layer**  
   - Manages multiple sessions over a single SSH connection.  
   - Supports functionalities such as:  
     - **Remote command execution**: Run shell commands on the remote server.  
     - **Secure file transfer**: Using protocols like SCP (Secure Copy) and SFTP (SSH File Transfer Protocol).  
     - **Port forwarding**: Redirect network traffic securely between systems.  

This layered design ensures secure, reliable, and scalable remote access across different use cases.

---

**How SSH Works**  

SSH establishes a secure connection through the following steps:  

1. **Handshake**  
   - The client initiates a connection by sending a request to the server.  
   - The server responds with its public key, initiating the cryptographic key exchange.  

2. **Authentication**  
   - The server authenticates the client using a selected method (e.g., password or public key).  
   - If the client’s credentials match, the server grants access.  

3. **Data Encryption**  
   - Once authentication succeeds, all subsequent communication is encrypted.  
   - This ensures that sensitive data, including commands and file transfers, remains confidential.  

---

**SSH Key Pair Generation**  

SSH uses a **public-private key pair** for secure authentication. Here’s how it works:  

- **Public Key**: Stored on the server. It enables the server to identify the client’s private key during authentication.  
- **Private Key**: Stored securely on the client’s machine. This key is never shared and is essential for completing the authentication process.  

To generate an SSH key pair, follow these steps:  

1. Open a terminal on your local machine.  
2. Run the following command:  
   ```bash
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   ```  
   - **`-t rsa`**: Specifies the RSA algorithm (widely used for SSH keys).  
   - **`-b 4096`**: Sets the key length to 4096 bits for enhanced security.  
   - **`-C`**: Adds a comment (often your email) to the key for identification.  

3. When prompted, specify the file path to save the key (or press Enter to use the default path: `~/.ssh/id_rsa`).  
4. Set a passphrase to add an extra layer of security to your private key.  

The key pair will be generated, with the public key stored in `id_rsa.pub` and the private key in `id_rsa`.  

---

**Using SSH Keys**  

1. **Copy the Public Key to the Server**  
   Use the following command to copy your public key to the server’s `~/.ssh/authorized_keys` file:  
   ```bash
   ssh-copy-id user@remote_host
   ```  

2. **Connect Using SSH**  
   Once the key is added, connect to the server without entering a password:  
   ```bash
   ssh user@remote_host
   ```  

---

**Advantages of Using SSH Keys**  
- **Enhanced Security**: Public key authentication is significantly more secure than passwords.  
- **Convenience**: Enables password-less login for trusted systems.  
- **Automation**: Useful for scripts and applications requiring remote access.  
- **Multi-Factor Authentication**: SSH keys can be combined with passphrases for added protection.  

---

**Common Use Cases of SSH**  

1. **Remote Command Execution**  
   Execute commands on remote servers securely:  
   ```bash
   ssh user@remote_host 'ls -la /var/www'
   ```  

2. **Secure File Transfer**  
   Transfer files using SCP:  
   ```bash
   scp file.txt user@remote_host:/path/to/destination
   ```  
   Or SFTP:  
   ```bash
   sftp user@remote_host
   ```  

3. **Port Forwarding**  
   Redirect traffic through an SSH tunnel:  
   ```bash
   ssh -L 8080:localhost:80 user@remote_host
   ```  

4. **Tunneling Services**  
   Encrypt connections to services like databases or web servers through SSH tunnels.  

---



# SSH Configuration Report  


## **Task 1: Configure Remote Access with Public Key**  

To eliminate the risks associated with password-based authentication, SSH was configured to use public-key authentication. The steps below detail the process:  

1. **Generate an SSH Key Pair**  
   - On the client machine, the following command was used to generate a 4096-bit RSA key pair:  
     ```bash
     ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
     ```  
   - The private key was stored securely on the client machine, and the public key was saved as `id_rsa.pub`.

2. **Copy the Public Key to the Server**  
   - The `ssh-copy-id` command was used to add the public key to the server's `~/.ssh/authorized_keys` file:  
     ```bash
     ssh-copy-id user@remote_host
     ```  
   - Alternatively, the public key was manually appended to the file:  
     ```bash
     cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
     ```  

3. **Disable Password-Based Authentication**  
   - To enhance security, the SSH server was configured to accept only public-key authentication:  
     - Edit the SSH configuration file:  
       ```bash
       sudo nano /etc/ssh/sshd_config
       ```  
     - Update the following parameters:  
       ```plaintext
       PasswordAuthentication no
       PubkeyAuthentication yes
       ```  
     - Restart the SSH service to apply changes:  
       ```bash
       sudo systemctl restart sshd
       ```  

4. **Test the Configuration**  
   - The client successfully accessed the server without entering a password:  
     ```bash
     ssh user@remote_host
     ```  

---

## **Task 2: Configure Two-Factor Authentication (2FA)**  

To strengthen authentication security, 2FA was configured on the server using Google Authenticator. Here’s how it was set up:  

1. **Install Google Authenticator**  
   - On the server, the following command was executed to install the PAM (Pluggable Authentication Module) for Google Authenticator:  
     ```bash
     sudo apt-get install libpam-google-authenticator
     ```  

2. **Set Up 2FA for the User**  
   - Each user configured their 2FA by running the following command:  
     ```bash
     google-authenticator
     ```  
   - Users were prompted to:
     - Scan the QR code using a 2FA app (e.g., Google Authenticator, Authy).  
     - Save the emergency backup codes.  
     - Enable time-based tokens.  

3. **Configure PAM for SSH**  
   - The PAM configuration was updated to enable 2FA:  
     ```bash
     sudo nano /etc/pam.d/sshd
     ```  
     - Add the following line:  
       ```plaintext
       auth required pam_google_authenticator.so
       ```  

4. **Update SSH Configuration**  
   - The SSH server configuration was modified to include 2FA:  
     ```bash
     sudo nano /etc/ssh/sshd_config
     ```  
     - Update or add these parameters:  
       ```plaintext
       ChallengeResponseAuthentication yes
       UsePAM yes
       ```  
   - Restart the SSH service:  
     ```bash
     sudo systemctl restart sshd
     ```  

5. **Verify 2FA**  
   - Upon SSH login, users were required to enter:  
     - Their private key passphrase (if used).  
     - A time-based 2FA code generated by the authenticator app.  

---

## **Task 3: Configure Log Rotation**  

To ensure system logs do not consume excessive disk space, log rotation was configured using the `logrotate` utility:  

1. **Install Logrotate**  
   - Logrotate was verified to be installed on the server:  
     ```bash
     sudo apt-get install logrotate
     ```  

2. **Configure Log Rotation for SSH Logs**  
   - A custom configuration file was created for SSH logs:  
     ```bash
     sudo nano /etc/logrotate.d/sshd
     ```  
   - The following rules were added to rotate SSH logs weekly and retain logs for four weeks:  
     ```plaintext
     /var/log/auth.log {
         weekly
         rotate 4
         compress
         delaycompress
         missingok
         notifempty
         create 0640 syslog adm
         sharedscripts
         postrotate
             systemctl reload sshd > /dev/null
         endscript
     }
     ```  

3. **Test Log Rotation**  
   - The configuration was tested to ensure proper rotation:  
     ```bash
     sudo logrotate -f /etc/logrotate.d/sshd
     ```  

4. **Verify Rotation**  
   - Old logs were archived, compressed, and stored as `.gz` files.  

---

## **Conclusion**  

The configurations implemented during this task significantly enhanced the server’s security and maintainability:  

1. Public-key authentication ensures secure, password-less login, mitigating brute-force attack risks.  
2. Two-factor authentication adds a critical second layer of security, protecting the system even if keys are compromised.  
3. Log rotation ensures efficient log management, preventing excessive disk space usage and ensuring compliance with logging standards.  

These measures collectively contribute to a robust and secure remote access environment.  

---  
