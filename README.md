# 🏥 MedVault — Decentralized Medical Data Vault

**Privacy-first. Complete Control over Medical Data. Powered by CESS Network.**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

---

## 🌐 Project Overview

**MedVault** is a decentralized application (**DApp**) designed to solve one of the most critical problems in modern healthcare: **patient sovereignty over medical data**.

By combining **CESS Network’s Encrypted Decentralized Object Storage (DeOSS)** with **EVM-compatible Smart Contracts**, MedVault eliminates centralized servers, trusted intermediaries, and password-based authentication.

This project does not merely rely on CESS for storage. It positions **CESS Network as the trust, integrity, and auditability layer** required for an ethical and decentralized future in digital healthcare.

---

## 🌍 Why CESS Network?

MedVault is an ideal real-world **Proof-of-Concept** for the CESS ecosystem:

- **Global Trust Layer**  
  CESS is used as an immutable source of truth through **Proof-of-Existence (PoE)**.

- **Healthcare-Critical Use Case**  
  Solves data silos, unauthorized sharing, and loss of patient control.

- **Ethical Infrastructure**  
  A censorship-resistant and decentralized alternative for sensitive medical records.

---

## 🧠 System Architecture — Pure Decentralization

MedVault follows a **fully decentralized hybrid architecture**, removing the need for any traditional backend server.

All responsibilities are distributed between the **client**, the **blockchain**, and **CESS DeOSS**.

---

### 🔹 1. Front-End (Client-Side)

The front-end is the orchestrator of the DApp.

All cryptography, authentication, file hashing, signature generation, and communication with both the blockchain and CESS DeOSS occur entirely on the client side.

**Core Technologies**
- Next.js  
- TypeScript  
- Ethers.js  
- MetaMask  
- CESS DeOSS REST API  

---

### 🔹 2. On-Chain Back-End (EVM Smart Contract)

The smart contract represents the **security and business logic layer**.

It is responsible for:
- Identity enforcement
- Ownership validation
- Time-based access control
- Immutable audit logs

**Main Functions**
- `uploadFile`
- `grantAccess`
- `revokeAccess`
- `hasAccess`
- `recordAccess`

---

### 🔹 3. Off-Chain Storage (CESS DeOSS)

Encrypted medical files are stored in **CESS DeOSS**, ensuring decentralized availability and integrity.

**CESS Guarantees**
- Data fragmentation
- Geo-redundancy
- Deduplication
- **PoDR²** (Proof of Data Reduplication and Recovery)

---

## 🎨 Front-End Functionalities — Patient Sovereignty

The user interface is designed around a single principle:

**Patients fully own, control, and audit access to their medical data.**

---

### 🔐 Wallet-Based Authentication

- Identity is the wallet address
- No passwords
- No centralized user accounts
- No credential storage

---

### 📤 Secure Upload to CESS DeOSS

Medical files are uploaded **directly from the browser** to CESS DeOSS.

```bash
PUT /file
# Required headers:
# Territory
# Account
# Message
# Signature
The gateway validates the cryptographic signature, ensuring authorization without exposing private keys.

⛓️ On-Chain and Immutable Registration

After a successful upload, the front-end registers immutable metadata on-chain:

fileHash — Cryptographic hash of the medical file

deossCID — File Identifier (FID) returned by CESS

owner — Wallet address of the patient

This guarantees ownership, integrity, and proof-of-existence.

🕒 Time-Limited Access Control

Patients can grant temporary read access to doctors or institutions.

Parameter	Description
File Hash	Unique identifier of the medical file
Doctor Address	Authorized professional or institution
Expiration Timestamp	Automatic access revocation time

Access rules are enforced on-chain, eliminating manual revocation and trust assumptions.

📜 Transparent and Verifiable Auditing

The front-end listens to smart contract events to build a complete audit trail:

FileRegistered

AccessGranted

AccessRevoked

FileAccessed

All actions are publicly verifiable and cryptographically immutable.

🚀 Next Evolution — Professional Healthcare Interface

The next milestone expands MedVault into a collaborative healthcare ecosystem.

Planned Feature	Strategic Benefit
Doctor Dashboard	View authorized files and expiration status
CESS PReT Integration	Proxy Re-Encryption for secure key delegation
Detailed Audit History	Proof of who accessed what and when

This evolution positions MedVault as a reference architecture for decentralized healthcare platforms.

🤝 Responsibility Matrix — Zero Trust Model

With no centralized backend, responsibilities are strictly separated.

Function	Front-End	Smart Contract	CESS DeOSS
Upload	File selection & REST call	Stores ownership & metadata	Stores encrypted file
Access Control	Selects recipient & duration	Executes permission logic	Enforces signature authorization
Retrieval	Requests download	Confirms permission (hasAccess)	Provides encrypted file data
Authentication	Wallet connection	Verifies ownership (msg.sender)	Requires gateway signature
📄 License

This project is licensed under the MIT License.

🇧🇷 Versão em Português
🏥 MedVault — Cofre Médico Descentralizado

Privacidade em primeiro lugar. Controle total sobre os dados médicos. Powered by CESS Network.

🌐 Visão Geral do Projeto

O MedVault é uma aplicação descentralizada (DApp) criada para resolver um dos maiores desafios da saúde digital: a soberania do paciente sobre seus próprios dados médicos.

Ao unir o Armazenamento Descentralizado Criptografado (DeOSS) da CESS Network com Smart Contracts compatíveis com EVM, o MedVault elimina servidores centrais, intermediários de confiança e autenticação baseada em senhas.

Mais do que usar a CESS, o projeto a estabelece como a infraestrutura de confiança, integridade e auditabilidade da saúde digital descentralizada.

🌍 Por que a CESS Network?

O MedVault demonstra:

Camada Global de Confiança
Uso da CESS como fonte imutável de verdade (Proof-of-Existence).

Caso de Uso Real em Saúde
Solução direta para silos de dados e falhas de privacidade médica.

Fundação Ética
Alternativa descentralizada, resiliente e segura para dados sensíveis.

🧠 Arquitetura — Descentralização Pura

O MedVault elimina completamente a necessidade de um backend centralizado.

🔹 1. Front-End (Cliente)

Toda a lógica ocorre no navegador

Criptografia e autenticação no lado do usuário

Tecnologias

Next.js

TypeScript

Ethers.js

MetaMask

API REST do CESS DeOSS

🔹 2. Back-End On-Chain (Smart Contract)

Responsável por identidade, propriedade e permissões.

Funções

uploadFile

grantAccess

revokeAccess

hasAccess

recordAccess

🔹 3. Armazenamento Off-Chain (CESS DeOSS)

Arquivos médicos criptografados

Fragmentação, geo-redundância e PoDR²

🎨 Funcionalidades do Front-End
🔐 Autenticação via Wallet

Sem senhas

Identidade = endereço da carteira

📤 Upload Seguro
PUT /file
# Headers obrigatórios:
# Territory
# Account
# Message
# Signature

⛓️ Registro Imutável On-Chain

Metadados registrados:

Hash criptográfico do arquivo

FID retornado pelo DeOSS

Endereço do proprietário

🕒 Controle de Acesso Temporal
Parâmetro	Função
Hash do Arquivo	Identifica o arquivo
Endereço do Médico	Profissional ou instituição autorizada
Timestamp de Expiração	Revogação automática do acesso
📜 Auditoria Transparente

Eventos monitorados:

FileRegistered

AccessGranted

AccessRevoked

FileAccessed

🚀 Próxima Evolução — Interface Profissional
Recurso Planejado	Benefício Estratégico
Dashboard do Médico	Visualização de acessos autorizados
Integração CESS PReT	Proxy Re-Encryption
Histórico Detalhado	Auditoria completa e verificável
🤝 Matriz de Responsabilidade
Função	Front-End	Smart Contract	CESS DeOSS
Upload	Seleção + REST	Metadados & ownership	Arquivo criptografado
Controle Acesso	Destinatário + tempo	Lógica de permissão	Regra de assinatura
Recuperação	Solicita download	Verifica acesso	Fornece arquivo
Autenticação	Conexão da wallet	msg.sender	Assinatura do gateway
📄 Licença

Este projeto está licenciado sob a Licença MIT.
