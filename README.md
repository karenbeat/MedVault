# 🏥 MedVault — Decentralized Medical Data Vault

**Privacy-first. Complete Control over Medical Data. Powered by CESS Network.**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

---

## 🌐 Project Overview

**MedVault** is a cutting-edge **Decentralized Application (DApp)** designed to solve one of the most critical challenges in digital healthcare: **patient sovereignty over medical data**.

By combining **CESS Network’s Encrypted Decentralized Object Storage (DeOSS)** with **EVM-based Smart Contracts**, MedVault removes centralized servers, trust intermediaries, and passwords from the healthcare data lifecycle.

This project does not merely *use* CESS Network for storage — it establishes CESS as the **trust, auditability, and integrity layer** required for an ethical and decentralized future in healthcare.

---

## 🌍 Why CESS Network?

MedVault is a strong **real-world Proof-of-Concept** for the CESS ecosystem, demonstrating:

- **Global Trust Layer**  
  Use of CESS as an immutable source of truth via **Proof-of-Existence (PoE)**.

- **Healthcare-Critical Use Case**  
  Direct solution to data silos, breaches, and lack of patient control.

- **Ethical Infrastructure**  
  A decentralized, censorship-resistant alternative for sensitive medical data.

---

## 🧠 System Architecture — Pure Decentralization

MedVault adopts a **fully decentralized hybrid architecture**, completely eliminating traditional backend servers.

All logic is distributed between the **client**, the **blockchain**, and **CESS DeOSS**.

### 🔹 1. Front-End (Client-Side)

The DApp orchestrator.  
All cryptography, authentication, and communication occur **entirely on the client**.

**Technologies**
- Next.js  
- TypeScript  
- Ethers.js  
- MetaMask  
- CESS DeOSS REST API  

---

### 🔹 2. On-Chain Back-End (EVM Smart Contract)

The security and business logic layer.

**Core Responsibilities**
- Identity management
- Ownership enforcement
- Time-based access control

**Main Functions**
- `uploadFile`
- `grantAccess`
- `revokeAccess`
- `hasAccess`
- `recordAccess`

---

### 🔹 3. Off-Chain Storage (CESS DeOSS)

Encrypted medical files are stored off-chain in **CESS DeOSS**.

**CESS Guarantees**
- Fragmentation
- Geo-redundancy
- Deduplication
- **PoDR²** (Proof of Data Reduplication and Recovery)

---

## 🎨 Front-End Functionalities (Patient Sovereignty)

The interface is designed with a single principle: **patients own and control their data**.

### 🔐 Wallet-Based Authentication
- Identity equals wallet address
- No passwords
- No centralized accounts

---

### 📤 Secure Upload (CESS DeOSS)

Files are uploaded **directly from the client** to DeOSS.

```bash
PUT /file
# Required headers:
# Territory
# Account
# Message
# Signature
