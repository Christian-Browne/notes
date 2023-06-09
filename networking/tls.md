# TLS

Transport Layer Security (TLS) is a cryptographic protocol that provides secure communication over a network, typically the internet. It ensures the confidentiality, integrity, and authenticity of data exchanged between two endpoints, such as a client and a server. TLS employs encryption algorithms to encrypt data during transmission, preventing unauthorized parties from intercepting and understanding the information. It also utilizes digital certificates to verify the identities of the communicating parties, ensuring that the data is being exchanged with the intended recipient. TLS is widely used in various applications, including web browsing, email, instant messaging, and file transfers, to establish a secure and trusted connection between clients and servers.

TLS handshake happens after TCP handhskae

- After client and server form connection using TCP handshake
- TLS handhskae happens

## TLS handshake

1. The client sends a "Hello" message to the server, telling it what TLS version and encryption methods it supports.
2. The server responds with its own "Hello" message, selecting a compatible TLS version and encryption method from the client's options.
3. The server sends its digital certificate, which includes a public key that the client can use to verify the server's identity.
4. The client checks the certificate and makes sure it's valid and trusted.
5. The client creates a secret key and encrypts it using the server's public key. This key will be used for secure communication.
6. Both the client and server independently generate the same session keys from the encrypted secret key.
7. They exchange messages to confirm that the handshake was successful and the connection is secure.

Once the handshake is complete, the client and server can start sending encrypted data to each other, ensuring that it's protected from eavesdropping and tampering. The TLS handshake establishes a secure connection by agreeing on encryption methods, verifying identities, and creating shared encryption keys.

## RSA Encryption (Diffie Hellman is better - go down the page)

To encrypt a message using RSA between a client and a server, the following steps are typically involved:

Generate RSA Key > Exchange public key > Encrypt message using public key > Decrypt message using private key

1. Key Generation:

   - The server generates an RSA key pair consisting of a public key and a private key.
   - The public key is shared with the client and can be freely distributed.
   - The private key is kept securely on the server and is not shared.

2. Public Key Exchange:

   - The client obtains the server's public key through a secure channel (such as a trusted certificate authority or key exchange protocol).

3. Message Encryption (Client):

   - The client takes the message that it wants to send and converts it into a suitable format for RSA encryption (usually by applying a padding scheme, such as PKCS#1).
   - The client uses the server's public key to encrypt the message, resulting in ciphertext.
   - The client sends the ciphertext to the server.

4. Message Decryption (Server):
   - The server receives the ciphertext from the client.
   - The server uses its private key to decrypt the ciphertext and recover the original message.
   - The decrypted message is now available for processing or further actions on the server side.

It's important to note that the encryption and decryption steps are performed by the client and the server, respectively. The client encrypts the message using the server's public key, ensuring that only the server with the corresponding private key can decrypt and read the message. This asymmetric encryption scheme provides confidentiality and secure communication between the client and the server.

Additionally, for secure transmission between the client and server, encryption protocols such as TLS (Transport Layer Security) or its predecessor SSL (Secure Sockets Layer) are commonly used. These protocols provide an additional layer of encryption and integrity verification to protect the data in transit.

## Diffie Hellman

- Has two private keys instead
- merging private and
- TLS1.3 uses this

The Diffie-Hellman key exchange algorithm allows two parties to establish a shared secret key over an insecure communication channel without prior sharing of any secrets. Here's a description of the algorithm:

1. Setup:

   - Both parties agree on a large prime number (p) and a base (g). These values are publicly known.

2. Private Key Generation:

   - Each party independently chooses a private key. Let's call them "a" for Party A and "b" for Party B.

3. Public Key Calculation:

   - Party A calculates A = g^a mod p.
   - Party B calculates B = g^b mod p.

4. Key Exchange:

   - Party A sends the calculated public key A to Party B.
   - Party B sends the calculated public key B to Party A.

5. Shared Secret Calculation:
   - Party A uses the received public key B and its own private key "a" to calculate the shared secret key: secret_key_A = B^a mod p.
   - Party B uses the received public key A and its own private key "b" to calculate the shared secret key: secret_key_B = A^b mod p.

Now, both Party A and Party B have independently computed the same shared secret key without directly exchanging it. This shared secret key can be used for symmetric encryption or any other cryptographic purposes.

The Diffie-Hellman algorithm enables secure key exchange in a way that even if an eavesdropper intercepts the public keys during transmission, it is computationally infeasible for them to derive the private keys or the shared secret key.

### Analogy

Setup:

- Both parties agree on a large prime number (p) and a base (g). These values are publicly known.

Private Key Generation:

- Each party independently chooses a private key. Let's call them "a" for Party A and "b" for Party B.

Public Key Calculation:

- Party A calculates A = g^a mod p.
- Party B calculates B = g^b mod p.

Key Exchange:

- Party A sends the calculated public key A to Party B.
- Party B sends the calculated public key B to Party A.

Shared Secret Calculation:

- Party A uses the received public key B and its own private key "a" to calculate the shared secret key: secret_key_A = B^a mod p.
- Party B uses the received public key A and its own private key "b" to calculate the shared secret key: secret_key_B = A^b mod p.

Now, both Party A and Party B have independently computed the same shared secret key without directly exchanging it. This shared secret key can be used for symmetric encryption or any other cryptographic purposes.

The Diffie-Hellman algorithm enables secure key exchange in a way that even if an eavesdropper intercepts the public keys during transmission, it is computationally infeasible for them to derive the private keys or the shared secret key.
