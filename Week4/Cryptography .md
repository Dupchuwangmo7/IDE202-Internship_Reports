# Cryptography 
Cryptography is a crucial tool for digital security, safeguarding information by ensuring **confidentiality**, **integrity**, and **authenticity**. It protects data during transmission and storage and secures interactions we use every day, often without direct user awareness.

### Everyday Examples of Cryptography

- **Login Credentials**: When logging in to websites (like TryHackMe), your credentials are encrypted before transmission, preventing interception by unauthorized parties.
  
- **SSH Connections**: For secure remote access, SSH creates an encrypted tunnel between client and server, ensuring privacy during the session.

- **Bank Certificates**: Cryptographic certificates confirm the authenticity of websites, like those of banks, to guard against phishing or impersonation attacks.

- **Checksum Verification**: When downloading files, cryptographic checksums confirm file integrity by comparing the downloaded file’s checksum to the expected one, verifying accuracy and completeness.

### Cryptography Standards in Data Protection

Sensitive data, especially financial or medical, must be encrypted to comply with regulations like **PCI-DSS** for payment card data or **GDPR** and **California Consumer Privacy Act (CCPA)** for general data privacy. These standards require data encryption both **at rest** (stored data) and **in transit** (data being sent over networks) to prevent unauthorized access.

### Password Management: Hashing vs. Encryption

Passwords should **not** be stored in plaintext. Instead of encryption (which is reversible), passwords should be **hashed** with a strong, one-way hashing function to store them safely. Hashing is ideal because it ensures that stored passwords are not directly recoverable. Encrypting passwords may be appropriate only for specific use cases, such as password managers, where decryption by the user is required.