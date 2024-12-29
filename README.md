# SSH-keys-based-authentication-configuration-with-Custom-Host
Tables of Contents

Authentication methods
Advantages of Public Key Authentication:
 Best Practices for Public Key Authentication:
Step 1: Generate SSH Key Pair
Step 2: Copy Public Key to Remote Host
Step 3: Test SSH Connection
Step 4: Optional - Create SSH Config File
Step 5: Connect Using SSH Config
Authentication methods
SSH supports two authentication methods:
1.Public key
2.Password

Public key authentication is a method of logging into an SSH/SFTP account using a cryptographic key pair rather than a password. This method provides a more secure way of authenticating compared to password-based authentication.

Here's how it works:

Key Generation: First, you generate a key pair on your local machine - a public key and a private key. The private key is kept secret on your local machine, while the public key can be shared freely.

Public Key Placement: You place the public key on the server you want to connect to. This is typically done by appending the contents of your public key file to the ~/.ssh/authorized_keys file on the server.

Authentication: When you attempt to connect to the server, your SSH client sends your public key to the server. The server checks if this public key is listed in the authorized_keys file. If it finds a matching public key, it generates a challenge using the public key and sends it to your client.

Private Key Usage: Your SSH client then uses your private key to decrypt the challenge and sends the decrypted response back to the server. If the server successfully decrypts the response using the corresponding public key, you are granted access.

Advantages of Public Key Authentication:
Enhanced Security: Public key authentication eliminates the need to transmit passwords over the network, reducing the risk of password interception.

Convenience: Once set up, public key authentication can offer a more seamless login experience compared to entering passwords, especially if you use SSH frequently.

Automation: Public key authentication can be easily integrated into automated scripts and processes, allowing for secure, passwordless authentication in various scenarios.

Best Practices for Public Key Authentication:
Protect Your Private Key: Keep your private key secure and never share it with anyone else. Use passphrase protection for added security.

Regular Key Rotation: Periodically rotate your SSH keys to mitigate the risk of key compromise.

Limited Access: Only grant access to authorized users by adding their public keys to the authorized_keys file on the server.

By using public key authentication, you can significantly enhance the security of your SSH connections while also streamlining the authentication process.
![image](https://github.com/user-attachments/assets/88eb6dc2-90ac-4e8a-870f-bc37ede3ca12)





  
