TrustVerify: File Integrity & Authenticity Tool

TrustVerify is a Python-based Command Line Interface (CLI) tool designed to ensure file integrity and origin verification using SHA-256 hashing and RSA digital signatures.

🛠 Features

File Hashing: Generates unique SHA-256 fingerprints for any file (Text, PDF, Images).

Manifest Generation: Scans a directory and creates a metadata.json to track file states.

Integrity Checking: Compares current file hashes against the manifest to detect unauthorized modifications (Data Tampering).

RSA Digital Signatures: Signs the manifest using a Private Key to ensure the sender's identity.

Signature Verification: Uses a Public Key to verify that the manifest is authentic and hasn't been altered.

🚀 Installation

Clone the repository:

git clone [YOUR_REPOSITORY_LINK]


Install the required library:
This tool uses the cryptography library for RSA signatures.

pip install cryptography


📖 Usage Guide

1. Key Generation

Generate your RSA Public/Private key pair:

python trust_verify.py keys


2. Protect Your Files (Sender)

Scan the directory to create a manifest and sign it:

python trust_verify.py init
python trust_verify.py sign


3. Verify Files (Receiver)

Check for file tampering and verify the sender's signature:

python trust_verify.py check
python trust_verify.py verify


📄 Technical Documentation

A detailed theoretical analysis of why hashing alone is insufficient and how RSA ensures non-repudiation can be found in the report.md file.

🎥 Demo Video

[Insert your Unlisted YouTube Video Link here]
Note: The demo covers key generation, manifest signing, and a demonstration of a failed verification after tampering with a file.

Developed by: Abd Eraouf GAGAA

Student ID: 210208707

Project: Mini Project I
