# SSH
SSH, or Secure Shell, is a protocol used for secure remote access and management of computers over an unsecured network. It works on a client-server model, establishing a secure communication channel to protect against unauthorized access and ensure data integrity. 

SSH consists of three layers:

1. **Transport Layer**: Manages encryption, decryption, data integrity checks, and performance optimizations.
2. **Authentication Layer**: Verifies the client's identity using methods like passwords, public keys, or certificates.
3. **Connection Layer**: Manages multiple sessions within one SSH connection, enabling secure file transfers, remote command execution, and port forwarding.

This layered approach ensures secure and flexible remote access.


SSH, or Secure Shell, establishes a secure connection between a client and server by using various authentication methods, including public keys, passwords, host keys, and sometimes security questions, to verify the client’s identity. After authentication, SSH encrypts all data transmitted between the client and server, maintaining confidentiality and preventing interception. 

This secure protocol is widely used by developers and system administrators across UNIX-based and Windows systems for managing remote access safely.

#### The SSH key generation process creates two keys:

- Public key. Installed on the server, allows the server to recognize and authenticate the client based on the matching private key.
- Private key. Must be kept secure. It is crucial for the authentication process to ensure that you are the only person who can authenticate to the server.
Follow the steps below to create the public-private key pair.

