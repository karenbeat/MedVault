# MedVault — Decentralized Platform for Secure Medical Data Storage and Controlled Sharing

> “MedVault demonstrates that decentralized storage is not merely a technological advancement, but a structural requirement for a future in which digital trust and privacy in healthcare are fundamentally protected.”

---

## Overview

MedVault is a decentralized application (DApp) built on the CESS Network, developed to redefine how sensitive medical data is stored, managed, and shared.  
The system leverages essential CESS components such as:

- DeOSS (Decentralized Object Storage System)
- Proxy Re-Encryption (PReT)
- Proof of Data Reduplication and Recovery (PoDR²)
- Proof of Existence (PoE)
- Multi-format Data Rights Confirmation (MDRC)

Together, these technologies ensure confidentiality, integrity, transparency, and long-term reliability for medical data.

MedVault empowers patients with complete sovereignty over their health records while enabling secure and revocable sharing with healthcare professionals.

---

## Motivation

Healthcare is one of the most vulnerable sectors concerning data breaches.  
IBM's Cybersecurity Report (2024) states that medical data can be up to **20 times more valuable** than financial information on the black market.

High-profile incidents such as **Project Nightingale** exposed structural flaws in centralized systems, where millions of patient records were accessed without explicit consent.

MedVault addresses these ethical and technical failures by leveraging the CESS Network to guarantee:

- Decentralized and tamper-proof data storage  
- End-to-end confidentiality via encryption and delegated cryptographic access  
- Transparent on-chain auditability  
- Removal of single points of failure  

---

## Objectives

### General Objective
Develop a decentralized system using the CESS Network to provide secure storage, controlled access, and verifiable auditing of medical files through smart contracts and distributed storage.

### Specific Objectives
- Implement Solidity smart contracts for ownership, permissions, and auditing  
- Integrate CESS DeOSS as the decentralized storage layer  
- Apply Proxy Re-Encryption (PReT) for secure delegated access  
- Utilize PoDR² and PoE for integrity and redundancy verification  
- Build a React-based front-end with MetaMask authentication  
- Demonstrate CESS Network as an ethical trust infrastructure for sensitive data  

---

# Front-End Architecture and Functionality

The front-end acts as a decentralized interface interacting with both the MedVault smart contract and the CESS DeOSS gateway. It was designed to ensure user sovereignty, transparency, and security.

## Technologies Used (Front-End)
- **Next.js / React**
- **TypeScript**
- **Ethers.js**
- **MetaMask Wallet Integration**
- **REST API Requests to DeOSS**

## Core Functionalities (Front-End)

### 1. Wallet Connection and Authentication
- The user connects via MetaMask.
- The wallet address is used to identify all previously uploaded files.
- All authentication is cryptographic; no centralized login exists.

### 2. File Upload to CESS DeOSS
- The user selects a file.
- The front-end sends it to DeOSS via `PUT /file`.
- Mandatory headers: `Territory`, `Account`, `Message`, `Signature`.

DeOSS responds with a unique **FID (File Identifier)**.

### 3. Smart Contract Registration
The front-end:
- Computes a file hash (SHA-256)
- Calls the contract to register:
  - fileHash  
  - deossCID (FID)  
  - timestamp  
  - wallet address  

### 4. Dashboard and File Management
- Displays the list of files owned by the connected wallet.
- Retrieves metadata directly from the smart contract.
- Allows file download from DeOSS.

### 5. Access Control UI
- Users select a file, choose a doctor’s wallet address, and set expiration.
- Calls `grantAccess` on the smart contract.

### 6. Audit Log Visualization
Listens to contract events:
- `FileUploaded`
- `AccessGranted`
- `FileAccessed`

Displayed as an immutable timeline.

### Front-End Security Principles
- No sensitive data is stored locally.
- All cryptographic operations run inside MetaMask.
- Optional AES/RSA encryption may occur client-side.

---

# Back-End Architecture and Functionality

MedVault adopts a decentralized back-end model composed of:

1. The **MedVault Smart Contract** (on-chain logic)  
2. The **CESS DeOSS Gateway** (off-chain encrypted storage)  

No centralized server is required.

---

## 1. Smart Contract Back-End (EVM-Based)

### Technologies
- Solidity 0.8.x  
- Sepolia Testnet  
- Blockchain event logging  

### Key Smart Contract Functions
- **uploadFile(fileHash, deossCID)** – Registers file metadata  
- **grantAccess(fileHash, doctor, expiration)** – Grants temporary access  
- **revokeAccess(fileHash, doctor)** – Revokes permissions  
- **hasAccess(fileHash, user)** – Validates user permissions  
- **recordAccess(fileHash)** – Records audit trail events  
- **verifyOwner(fileHash)** – Confirms file ownership  

### Decentralization Advantages
- Immutable audit history  
- No dependence on centralized authentication  
- Transparent and verifiable interactions  
- Eliminates trust requirements between participants  

---

## 2. CESS DeOSS Storage Back-End

Responsible for storing encrypted medical data.

### Technologies
- CESS DeOSS (v0.4+)  
- REST API communication  
- Territory authorization system  
- Gateway signature authentication  

### Core Functionalities (DeOSS)
- Upload: `PUT /file`  
- Download: `GET /file/download/<fid>`  
- Metadata: `GET /file/metadata/<fid>`  
- Deletion: `DELETE /file/<fid>`  

### Resilience and Redundancy
- Geographic replication  
- Fragmentation and deduplication  
- PoDR²-based recovery  
- Anti-tampering integrity via PoE  

---

# Interaction Model: Front-End × Smart Contract × DeOSS

| Function | Front-End | Smart Contract | DeOSS |
|---------|-----------|----------------|--------|
| Upload | Sends file; computes hash | Stores metadata | Stores file |
| Download | Requests file | Validates permissions | Returns encrypted file |
| Access Control | UI for sharing rules | Stores access rights | Enforces access |
| Audit | Displays logs | Emits events | — |
| Authentication | MetaMask signature | Verifies msg.sender | Requires signed headers |

This architecture ensures a fully decentralized trust model built upon transparency, cryptographic verification, and distributed storage.

---

# Project Timeline

| Stage | Description | Period |
|-------|-------------|--------|
| 1 | Research and analysis; CESS infrastructure study | Completed |
| 2 | Smart contract development | Oct 10 – Oct 14 |
| 3 | DeOSS and PoE integration | Oct 15 – Oct 20 |
| 4 | React interface and cryptography module | Oct 21 – Oct 26 |
| 5 | Testing, documentation, final submission | Oct 28 – Nov 6 |

---

# Conclusion

MedVault positions the CESS Network at the forefront of digital trust and decentralized health data governance.  
The project demonstrates that:

- privacy is a fundamental right,  
- decentralization is essential for medical ethics,  
- and CESS provides the infrastructure required for secure, transparent, and resilient data systems.

MedVault establishes a blueprint for future healthcare applications built on Web3 principles.

---

# References

- Identity Management Institute. *Blockchain for Healthcare Data Security*, 2024.  
- IBM Security. *Cost of a Data Breach Report*, 2024.  
- Google & Ascension. *Project Nightingale Case Study*, 2024.  
- SpringerLink. *Hybrid Blockchain Models for Health Data Privacy*, 2024.  
- Nature Scientific Reports. *Blockchain Applications in Healthcare*, 2025.  
- STL Partners. *Blockchain Use Cases in Digital Health*, 2024.  

---

# Portuguese Translation — Versão Profissional

## Visão Geral

O MedVault é uma aplicação descentralizada construída na CESS Network para redefinir o armazenamento, o gerenciamento e o compartilhamento de dados médicos sensíveis. O projeto utiliza os principais mecanismos da CESS — DeOSS, PReT, PoDR², PoE e MDRC — para garantir integridade, segurança e governança transparente.

O sistema devolve ao paciente o controle total de seus dados, permitindo compartilhamento seguro e revogável com profissionais de saúde.

---

## Motivação

O setor de saúde apresenta índices críticos de violações de dados.  
Registros médicos são extremamente valiosos e frequentemente alvo de ataques.  
Casos como o Project Nightingale evidenciam riscos estruturais de sistemas centralizados.

O MedVault utiliza a CESS Network para garantir:

- Armazenamento descentralizado e imutável  
- Confidencialidade por criptografia  
- Auditoria transparente  
- Eliminação de intermediários centralizados  

---

## Objetivos

### Objetivo Geral
Desenvolver um sistema descentralizado baseado na CESS Network para garantir armazenamento seguro e compartilhamento controlado de arquivos médicos.

### Objetivos Específicos
- Criar contratos inteligentes em Solidity  
- Integrar o DeOSS como camada de armazenamento  
- Implementar PReT para acesso delegado  
- Utilizar PoDR² e PoE  
- Construir interface React com MetaMask  
- Demonstrar a CESS como infraestrutura de confiança  

---

# Arquitetura e Funcionamento do Front-End

O front-end funciona como uma interface descentralizada que interage diretamente com o DeOSS e com o contrato inteligente.

## Tecnologias
- Next.js / React  
- TypeScript  
- Ethers.js  
- MetaMask  
- REST para DeOSS

## Funcionalidades
- Autenticação via MetaMask  
- Upload de arquivos ao DeOSS  
- Registro on-chain dos metadados  
- Dashboard de arquivos  
- Controle de acesso  
- Exibição de logs de auditoria  

---

# Arquitetura e Funcionamento do Back-End

O back-end é descentralizado e dividido em duas partes: contrato inteligente e DeOSS.

## 1. Contrato Inteligente
- Registro de arquivos  
- Controle de permissões  
- Auditoria via eventos  
- Validação de proprietário  

## 2. DeOSS
- Upload, download e metadados  
- Assinatura e autorização via cabeçalhos  
- Replicação, deduplicação e PoDR²  
- Integridade via PoE  

---

# Modelo de Interação

| Ação | Front-End | Smart Contract | DeOSS |
|------|-----------|----------------|--------|
| Upload | Envia arquivo | Registra metadados | Armazena arquivo |
| Download | Solicita | Valida permissão | Entrega arquivo |
| Permissões | UI | Lógica de acesso | — |
| Auditoria | Exibe | Gera eventos | — |

---

# Cronograma

(igual à versão em inglês)

---

# Conclusão

O MedVault estabelece um novo paradigma de governança para dados médicos, demonstrando que a descentralização é essencial para segurança, transparência e ética digital.

---

# Autora
Karen Beatrice Souza Gonçalves  
Universidade de Brasília (UnB)  
GitHub: https://github.com/karenbeat
