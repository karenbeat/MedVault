🏥 MedVault

Decentralized Medical Data Vault powered by CESS Network

Privacy-first, decentralized infrastructure for secure medical data storage and controlled sharing.

🌐 Overview

MedVault is a fully decentralized application (DApp) designed to give patients full sovereignty over their medical data.
By combining CESS DeOSS for encrypted off-chain storage with EVM smart contracts for immutable access control, MedVault removes centralized servers, credentials, and trust intermediaries.

This project positions CESS Network as a trust infrastructure, not merely a storage provider.

🧠 System Architecture

MedVault follows a hybrid decentralized architecture composed of three independent layers:

🔹 Front-End (Client-Side)

Wallet-based authentication

Client-side cryptography

Direct interaction with DeOSS and smart contracts

🔹 On-Chain Back-End

Smart contracts manage:

File ownership

Time-based access permissions

Audit logs and verification

🔹 Off-Chain Storage

Encrypted medical files stored in CESS DeOSS

Fragmentation, redundancy, and recovery guarantees

There is no centralized backend server.

🎨 Front-End Architecture & Functionality

The front-end acts as a decentralized orchestrator, connecting users directly to the blockchain and the CESS DeOSS gateway.

Core Technologies

Next.js (React)

TypeScript

Ethers.js

MetaMask

CESS DeOSS REST API

Key Features
🔐 Wallet Authentication

Authentication exclusively via MetaMask

No passwords or centralized accounts

Wallet address defines identity and ownership

📤 File Upload to CESS DeOSS

Files uploaded directly from the browser using REST

Required headers:

Territory

Account

Message

Signature

DeOSS returns a FID (File Identifier)

PUT /file

⛓️ On-Chain Metadata Registration

After upload:

A cryptographic hash is generated client-side

The smart contract stores:

fileHash

deossCID (FID)

timestamp

owner address

This guarantees immutability and proof of ownership.

📊 Dashboard & File Management

Lists all files owned by the connected wallet

Metadata fetched directly from the blockchain

Files downloaded directly from DeOSS

🕒 Access Control

Owners grant time-limited access to doctors or institutions

Parameters:

File hash

Recipient wallet address

Expiration timestamp

Permissions enforced on-chain

📜 Audit Logs

UI listens to smart contract events:

FileRegistered

AccessGranted

AccessRevoked

FileAccessed

Provides an immutable access timeline

🔐 Security Principles

No private keys stored
