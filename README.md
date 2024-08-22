# Quantum-Resistant Cryptographic Module

## Overview

The Quantum-Resistant Cryptographic Module provides a set of cryptographic functions designed to secure data and transactions against potential quantum computing threats. This module includes key management, encryption, and digital signature functionality with quantum-resistant algorithms.

## Features

- **Quantum-Resistant Key Management**: Generate quantum-resistant key pairs.
- **Encryption and Decryption**: Encrypt and decrypt data securely using quantum-resistant algorithms.
- **Digital Signatures**: Sign and verify transactions to ensure data integrity and authenticity.

## Recent Changes

- **Updated Signature Logic**: Improved the signing and verification functions to ensure consistency and accuracy in signature verification. The new logic uses a cyclic approach to handle cases where the key length is shorter than the data length.

## Getting Started

### Installation

To use this module in your Rust project, add it as a dependency in your `Cargo.toml` file:

```toml
[dependencies]
quantum_resistant_crypto = { path = "../quantum_resistant_crypto" }

Usage
Below is an example of how to use the Quantum-Resistant Cryptographic Module:

use quantum_resistant_crypto::key_management::QuantumKeyPair;
use quantum_resistant_crypto::encryption::{encrypt_data, decrypt_data};
use quantum_resistant_crypto::signature::{sign_transaction, verify_signature};

fn main() {
    // Generate Quantum-Resistant Key Pair
    let keypair = QuantumKeyPair::generate();
    println!("Generated Quantum-Resistant Public Key: {:?}", keypair.public_key);
    println!("Generated Quantum-Resistant Private Key: {:?}", keypair.private_key);

    // Encrypt Data
    let data = b"Sensitive transaction data";
    let encrypted_data = encrypt_data(&keypair.public_key, data);
    println!("Encrypted Data: {:?}", encrypted_data);

    // Decrypt Data
    let decrypted_data = decrypt_data(&keypair.private_key, &encrypted_data);
    println!("Decrypted Data: {:?}", String::from_utf8(decrypted_data).unwrap());

    // Sign Data
    let signature = sign_transaction(&keypair.private_key, data);
    println!("Signature: {:?}", signature);

    // Verify Signature
    let is_valid = verify_signature(&keypair.public_key, data, &signature);
    println!("Is the signature valid? {}", is_valid);
}

Contributing
Fork the repository.
Create a new branch for your changes.
Make your changes and update the README.md as needed.
Submit a pull request with a description of your changes.
License
This project is licensed under the MIT License. See the LICENSE file for more details.

Contact

For questions or feedback, please contact charlesDef@ubs.com.
