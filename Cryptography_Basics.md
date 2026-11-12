Cryptography Basics

Core Terminology & Goals
Cryptography: The practice of using math to protect data from unauthorized access. It turns
readable data (Plaintext) into unreadable scrambled data (Ciphertext) using an algorithm and
a secret Key. Turning it back is called Decryption.
The 4 Goals (CIA + N):
Confidentiality: Only authorized people with the right key can read the data.
Integrity: Ensures the data has not been changed or tampered with.
Authentication: Verifies the true identity of the sender and receiver.
Non-repudiation: Prevents a sender from denying that they sent a message.
Symmetric vs. Asymmetric Encryption
Symmetric Encryption: Uses the same secret key for both encrypting and decrypting data. It is
like a single secret code that both the sender and receiver share.
Pros: Very fast and efficient for large amounts of data.
Cons: The key must be safely shared between parties beforehand, which creates a security
risk.
Common Examples: AES, ChaCha20, DES (older/insecure).
Asymmetric Encryption: Uses a pair of mathematically linked keys: a public key (shared with
everyone) and a private key (kept strictly secret). Data locked with the public key can only be
unlocked with the matching private key.
Pros: Highly secure for sharing keys; you never have to send your private key over the
internet.
Cons: Much slower than symmetric encryption due to heavy math.
Common Examples: RSA, ECC (Elliptic Curve Cryptography), Diffie-Hellman.
Hashing (MD5, SHA-256)
Hashing is a one-way process that takes data of any size and turns it into a fixed-size string of
characters called a hash or digest. Unlike encryption, hashing cannot be reversed to get the
original data back.
MD5 (Message Digest 5): An older hashing algorithm that produces a 128-bit hash. It is
now considered broken and insecure because attackers can easily create collisions (two
different files that produce the exact same hash).
SHA-256 (Secure Hash Algorithm 256-bit): A modern, secure algorithm that produces a
256-bit hash. Even changing a single letter in the original file creates a completely different hash
(known as the avalanche effect).
Main Use: Verifying data integrity and safely storing passwords (when combined with a
random string called a "salt").
Digital Signatures, Certificates & SSL/TLS
These tools work together to verify identity and secure communication across the internet.
Digital Signatures: A mathematical stamp created using a sender's private key. Anyone
with the sender's public key can check the signature to prove who sent the file and confirm it
wasn't altered.
Digital Certificates: Digital ID cards that verify the identity of a website or server. A
certificate links a website's public key to its real-world identity and is signed by a trusted third

party called a Certificate Authority (CA).
SSL/TLS (Secure Sockets Layer / Transport Layer Security): Cryptographic protocols
that encrypt traffic between your web browser and a website. When you visit an HTTPS site,
your browser checks its digital certificate, uses asymmetric encryption to safely share a session
key, and then uses fast symmetric encryption for the rest of your visit.
Hands-on: OpenSSL Commands
OpenSSL is a popular command-line tool used to test encryption, generate keys, and create
hashes. Here are the most common commands for hands-on practice:
To Encrypt a File (AES-256):
openssl enc -aes-256-cbc -pbkdf2 -in input.txt -out encrypted.enc
To Decrypt a File:
openssl enc -d -aes-256-cbc -pbkdf2 -in encrypted.enc -out decrypted.txt
To Generate a SHA-256 Hash:
openssl dgst -sha256 input.txt
To Generate an RSA Private Key:
openssl genpkey -algorithm RSA -out private_key.pem -pkeyopt rsa_keygen_bits:2048
