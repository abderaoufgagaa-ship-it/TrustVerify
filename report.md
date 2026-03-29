TrustVerify Technical Report

Student Name: Abd Eraouf GAGAA
Student ID: 210208707
Project: Mini Project I: "TrustVerify" – CLI Tool for File Integrity

1. Why Hashing Alone Isn't Enough to Prove Identity

Hashing (specifically SHA-256) is a cryptographic function that ensures Integrity. It provides a unique fingerprint for a file, allowing a receiver to detect if a single bit has been changed since the hash was generated.

However, hashing alone cannot provide Authenticity or Identity proof for the following reasons:

The Vulnerability: If an attacker intercepts a file and its corresponding metadata.json, they can modify the file, generate a new SHA-256 hash for the modified file, and update the metadata.json accordingly.

The Result: The receiver will check the hash, find that it matches the (malicious) file, and wrongly assume the data is untampered. Hashing proves the file hasn't changed since the hash was generated, but it doesn't prove who generated the hash.

2. Non-Repudiation and the RSA Key Relationship

Digital Signatures using RSA solve the identity problem through the mathematical relationship between a Public and a Private key (Asymmetric Encryption).

The Mechanism:

Private Key: Known only to the sender. It is used to "sign" the hash of the manifest. Since the private key is unique to the sender and kept secret, the signature acts as a secure digital seal that only they can create.

Public Key: Shared openly with the receiver. It is used to verify that the signature was indeed created by the corresponding private key.

Ensuring Non-Repudiation:

Non-repudiation is the assurance that a party cannot deny the validity of a statement or contract. In this project:

Because the Private Key is kept secret by the sender, only they could have produced a valid signature that corresponds to their Public Key.

If the Public Key successfully verifies the signature, it provides mathematical proof of two things:

Integrity: The data (the manifest) has not been tampered with since it was signed.

Authenticity: The document originated from the specific owner of the Private Key.

Consequently, the sender cannot "repudiate" or deny having sent the file, as no one else could have produced that specific signature.
