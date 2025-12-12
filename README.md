project:
  name: MedVault
  tagline: Decentralized Medical Data Vault built on CESS Network and EVM-compatible blockchains
  license: MIT

overview:
  description: >
    MedVault is a fully decentralized application designed to provide secure,
    auditable, and user-sovereign storage of sensitive medical data.
    The platform combines CESS DeOSS for encrypted off-chain storage with
    smart contracts for immutable ownership, access control, and auditability.
  principles:
    - No centralized servers
    - No centralized credentials
    - Cryptographic ownership and permissions
    - Transparency by default

architecture:
  model: Hybrid Decentralized Architecture
  centralized_backend: false
  components:
    front_end:
      description: >
        Client-side decentralized interface responsible for wallet authentication,
        encryption, file upload, and smart contract interaction.
    on_chain_back_end:
      description: >
        Smart contracts deployed on an EVM-compatible blockchain manage file
        ownership, access permissions, and audit logs.
    off_chain_storage:
      description: >
        CESS DeOSS stores encrypted medical files and provides redundancy,
        integrity verification, and recovery guarantees.

front_end:
  role: >
    Acts as a decentralized orchestrator between the user,
    the blockchain, and the CESS DeOSS gateway.
  technologies:
    - Next.js (React)
    - TypeScript
    - Ethers.js
    - MetaMask
    - CESS DeOSS REST API

  features:
    wallet_authentication:
      description: >
        Users authenticate exclusively through MetaMask.
        No passwords, usernames, or centralized identity providers are used.
      properties:
        - Wallet address defines ownership
        - Wallet address defines access permissions

    file_upload:
      description: >
        Files are uploaded directly from the client to a CESS DeOSS gateway
        using REST APIs.
      required_headers:
        - Territory
        - Account
        - Message
        - Signature
      response:
        fid: File Identifier returned by DeOSS

    on_chain_registration:
      description: >
        After upload, the client computes a cryptographic hash of the file
        and registers metadata on-chain.
      stored_metadata:
        - fileHash
        - deossCID
        - timestamp
        - ownerAddress

    dashboard:
      description: >
        Displays all files owned by the connected wallet.
        Metadata is retrieved directly from the blockchain.
      capabilities:
        - File listing
        - Direct download from DeOSS

    access_control:
      description: >
        File owners can grant time-limited access to third parties
        such as doctors or institutions.
      parameters:
        - fileHash
        - recipientWallet
        - expirationTimestamp

    audit_logs:
      description: >
        The front-end listens to smart contract events
        and displays an immutable audit trail.
      events:
        - FileRegistered
        - AccessGranted
        - AccessRevoked
        - FileAccessed

front_end_security:
  principles:
    - No private keys stored
    - All cryptographic operations occur inside MetaMask
    - Optional client-side encryption (AES / RSA)
    - Communication restricted to trusted endpoints

back_end:
  model: Fully Decentralized

  smart_contract:
    description: >
      The smart contract defines ownership, permissions, and auditability.
      It does not store files, only metadata.
    technologies:
      - Solidity ^0.8.x
      - EVM-compatible blockchain (Sepolia Testnet)
    main_functions:
      - registerFile(fileHash, fid)
      - grantAccess(fileHash, user, expiration)
      - revokeAccess(fileHash, user)
      - hasAccess(fileHash, user)
      - getMyFiles()
      - getFileInfo(fileHash)

  deoss:
    description: >
      CESS DeOSS is responsible for encrypted off-chain storage of medical files.
    capabilities:
      - Encrypted object storage
      - Fragmentation and redundancy
      - Deduplication and recovery
      - Proof of Existence (PoE)
      - Proof of Data Reduplication and Recovery (PoDR²)
    endpoints:
      upload: PUT /file
      download: GET /file/download/<fid>
      metadata: GET /file/metadata/<fid>
      delete: DELETE /file/<fid>

future_improvements:
  doctor_interface:
    description: >
      A dedicated interface for doctors to securely access shared medical data.
    planned_features:
      - Doctor-specific dashboard
      - Read-only access to authorized files
      - Access expiration indicators
      - Auditable access history
      - Integration with CESS Proxy Re-Encryption (PReT)

cess_value_proposition:
  description: >
    MedVault demonstrates CESS Network as a global trust infrastructure
    for sensitive medical data and decentralized healthcare applications.
