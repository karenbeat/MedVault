

# 🏥 MedVault — Decentralized Medical Data Vault

**Privacy-first. Complete Control over Medical Data. Powered by CESS Network.**

- - -

## 📤 Secure Upload to CESS DeOSS

Medical files are uploaded **directly from the browser** to **CESS DeOSS**, without passing through centralized servers.

```
PUT /file
# Required headers:
# Territory
# Account
# Message
# Signature
```

The gateway validates the **cryptographic signature**, ensuring authorization **without exposing private keys**.

## ⛓️ On-Chain and Immutable Registration

After a successful upload, the front-end registers **immutable metadata on-chain**:

*   **fileHash** — Cryptographic hash of the medical file
*   **deossCID** — File Identifier (FID) returned by CESS
*   **owner** — Wallet address of the patient

This guarantees **ownership**, **integrity**, and **proof-of-existence**.

## 🕒 Time-Limited Access Control

Patients can grant **temporary read access** to doctors or institutions.

| Parameter | Description |
| --- | --- |
| File Hash | Unique identifier of the medical file |
| Doctor Address | Authorized professional or institution |
| Expiration Timestamp | Automatic access revocation time |

Access rules are **enforced on-chain**, eliminating manual revocation and trust assumptions.

## 📜 Transparent and Verifiable Auditing

The front-end listens to smart contract events to build a **complete audit trail**:

*   `FileRegistered`
*   `AccessGranted`
*   `AccessRevoked`
*   `FileAccessed`

All actions are **publicly verifiable** and **cryptographically immutable**.

## 🚀 Next Evolution — Professional Healthcare Interface

The next milestone expands MedVault into a **collaborative healthcare ecosystem**.

| Planned Feature | Strategic Benefit |
| --- | --- |
| Doctor Dashboard | View authorized files and expiration status |
| CESS PReT Integration | Proxy Re-Encryption for secure key delegation |
| Detailed Audit History | Proof of who accessed what and when |

This evolution positions MedVault as a **reference architecture** for decentralized healthcare platforms.

## 🤝 Responsibility Matrix — Zero Trust Model

With no centralized backend, responsibilities are **strictly separated**.

| Function | Front-End | Smart Contract | CESS DeOSS |
| --- | --- | --- | --- |
| Upload | File selection & REST call | Stores ownership & metadata | Stores encrypted file |
| Access Control | Selects recipient & duration | Executes permission logic | Enforces signature authorization |
| Retrieval | Requests download | Confirms permission (hasAccess) | Provides encrypted file data |
| Authentication | Wallet connection | Verifies ownership (msg.sender) | Requires gateway signature |

## 📄 License

This project is licensed under the **MIT License**.

- - -

# 🇧🇷 MedVault — Cofre de Arquivos Médicos Descentralizados

**Privacidade em primeiro lugar. Controle total sobre os dados médicos. Powered by CESS Network.**

## 🌐 Visão Geral do Projeto

O **MedVault** é uma aplicação descentralizada (**DApp**) criada para resolver um dos maiores desafios da saúde digital: **a soberania do paciente sobre seus próprios dados médicos**.

Ao unir o **Armazenamento Descentralizado Criptografado (DeOSS)** da CESS Network com **Smart Contracts compatíveis com EVM**, o MedVault elimina servidores centrais, intermediários de confiança e autenticação baseada em senhas.

Mais do que usar a CESS, o projeto a estabelece como a **infraestrutura de confiança, integridade e auditabilidade** da saúde digital descentralizada.

## 📄 Licença

Este projeto está licenciado sob a **Licença MIT**.
