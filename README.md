# zkChainSEAL

<div align="center">

### Blockchain-based Secure Digital Evidence Management System

*A secure, transparent, and tamper-resistant platform for managing digital forensic evidence using Ethereum-compatible smart contracts, zkSync Era, and decentralized storage.*

<br>

![Solidity](https://img.shields.io/badge/Solidity-0.8.x-363636?logo=solidity)
![React](https://img.shields.io/badge/React-19.x-61DAFB?logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?logo=typescript)
![Foundry](https://img.shields.io/badge/Foundry-Forge-orange)
![zkSync](https://img.shields.io/badge/zkSync-Era-8C8DF7)
![Ethereum](https://img.shields.io/badge/Ethereum-Sepolia-3C3C3D?logo=ethereum)
![License](https://img.shields.io/badge/License-MIT-green)

</div>

---

## Overview

**zkChainSEAL** is a blockchain-powered digital evidence management system designed to ensure the integrity, authenticity, and traceability of forensic evidence throughout its lifecycle.

The project combines **Ethereum-compatible smart contracts**, **zkSync Era**, **IPFS**, and **MetaMask** to build a secure evidence management platform where evidence integrity can be independently verified while minimizing storage costs through decentralized content-addressable storage.

Originally developed as an Ethereum-based implementation, the project has been extended to **zkSync Era** to improve scalability, reduce transaction costs, and explore Layer-2 blockchain solutions for digital forensics.

The repository currently serves as both:

- an open-source blockchain application, and
- a research prototype for secure blockchain-based digital evidence management.


> **Project Status**
>
> 🟢 Active Development
>
> The **`zksync-integration`** branch is the primary development branch and contains the latest features and improvements.
>
> The **`ethereum-baseline`** branch is maintained as a stable reference implementation.


# Table of Contents

- [Project Overview](#project-overview)
- [Motivation](#motivation)
- [Key Features](#key-features)
- [System Architecture](#system-architecture)
- [Technology Stack](#technology-stack)
- [Repository Structure](#repository-structure)
- [Branch Structure](#branch-structure)
- [Evidence Lifecycle](#evidence-lifecycle)
- [Getting Started](#getting-started)
- [Environment Variables](#environment-variables)
- [Running the Project](#running-the-project)
- [Smart Contract Overview](#smart-contract-overview)
- [Security Considerations](#security-considerations)
- [Contributing](#contributing)
- [Current Limitations](#current-limitations)
- [Future Work](#future-work)
- [Research Context](#research-context)
- [Acknowledgements](#acknowledgements)
- [License](#license)
- [Contact](#contact)

---

# Project Overview

Digital evidence plays a critical role in modern criminal investigations, cybercrime analysis, digital forensics, and judicial proceedings. As investigations increasingly rely on digital artifacts such as documents, images, videos, emails, and system logs, ensuring the authenticity and integrity of this evidence has become a fundamental requirement.

Most existing evidence management systems are built on centralized architectures where a single organization maintains ownership of the database. Although widely adopted, these systems present several challenges, including limited transparency, potential risks of unauthorized data modification, single points of failure, and difficulties in independently verifying the complete chain of custody.

zkChainSEAL addresses these challenges by integrating blockchain technology with decentralized storage to create a transparent and tamper-resistant digital evidence management platform. Instead of storing evidence files directly on the blockchain, the system stores only cryptographic hashes and essential metadata on-chain, while the actual evidence is securely stored using the InterPlanetary File System (IPFS). This hybrid architecture preserves evidence integrity while significantly reducing blockchain storage costs.

The project was initially developed on Ethereum Sepolia to demonstrate secure evidence registration and verification using smart contracts. To improve scalability and reduce transaction costs, the implementation has been extended to **zkSync Era**, an Ethereum Layer-2 network that provides lower gas fees while maintaining Ethereum compatibility.

zkChainSEAL serves as both an open-source software project and a research prototype exploring the application of blockchain technology for secure digital evidence management.


## Motivation

Digital forensic investigations demand complete confidence that evidence has not been modified from the moment it is collected until it is presented in court. Even a minor alteration can compromise the credibility and admissibility of evidence, making secure evidence preservation an essential requirement.

Traditional evidence management systems rely primarily on centralized databases and administrative controls to maintain integrity. While these systems are effective for routine operations, they often depend on trusted authorities and may provide limited transparency for independent verification.

Blockchain technology introduces a fundamentally different trust model by maintaining an immutable, distributed ledger that records every authorized transaction. Once evidence metadata is committed to the blockchain, it becomes computationally impractical to modify or remove without detection. This property makes blockchain particularly well suited for preserving the integrity and traceability of forensic evidence.

However, storing complete evidence files directly on-chain is both technically impractical and economically expensive. Large multimedia files can dramatically increase storage costs and reduce system scalability.

zkChainSEAL overcomes this limitation by combining blockchain with decentralized storage:

- Evidence files are stored in **IPFS**.
- Cryptographic hashes are recorded on the blockchain.
- Metadata is maintained for efficient retrieval and management.
- Smart contracts enforce authorization and evidence registration.
- Users can independently verify evidence integrity by comparing newly generated hashes with the immutable blockchain record.

This architecture provides a practical balance between decentralization, scalability, security, and cost efficiency.


## Problem Statement

Digital evidence management systems must satisfy several fundamental security and operational requirements:

- Preserve the integrity of digital evidence throughout its lifecycle.
- Maintain a verifiable chain of custody.
- Prevent unauthorized modification or deletion of evidence records.
- Enable transparent and independent evidence verification.
- Reduce dependence on centralized trust.
- Support scalable storage of large digital artifacts.

Conventional database-driven solutions address some of these requirements but often struggle to simultaneously provide immutability, transparency, decentralization, and efficient storage.

zkChainSEAL proposes a blockchain-based architecture that combines smart contracts, decentralized storage, and cryptographic verification to address these challenges.


## Project Objectives

The primary objectives of zkChainSEAL are:

- Develop a secure blockchain-based platform for managing digital forensic evidence.
- Ensure evidence integrity using cryptographic hashing and immutable blockchain records.
- Store large evidence files efficiently using IPFS while maintaining on-chain verification.
- Implement role-based access control using Ethereum-compatible smart contracts.
- Reduce blockchain transaction costs through zkSync Era Layer-2 integration.
- Provide an extensible research platform for evaluating blockchain technologies in digital forensics.
- Demonstrate a practical architecture that balances security, scalability, transparency, and cost.


## Why Blockchain?

Blockchain technology provides several properties that directly address the requirements of secure evidence management:

| Requirement | Blockchain Benefit |
|------------|--------------------|
| Data Integrity | Immutable records prevent undetected modification. |
| Chain of Custody | Every authorized operation is permanently recorded. |
| Transparency | Evidence records can be independently verified. |
| Authentication | Wallet-based identities authenticate authorized users. |
| Auditability | Transaction history provides a complete audit trail. |
| Trust | Verification depends on cryptographic proofs rather than a single trusted authority. |

Rather than replacing existing evidence management systems, blockchain acts as an immutable trust layer that strengthens the integrity and verifiability of stored evidence.


## Why zkSync Era?

Ethereum provides strong security guarantees but transaction fees and throughput limitations can become significant as application usage increases.

zkSync Era is an Ethereum Layer-2 scaling solution that executes transactions off-chain while inheriting Ethereum's security model through zero-knowledge proofs.

The migration to zkSync Era enables zkChainSEAL to:

- Reduce transaction costs.
- Improve transaction throughput.
- Maintain Ethereum Virtual Machine (EVM) compatibility.
- Preserve existing smart contract workflows with minimal modifications.
- Provide a scalable foundation for future blockchain-based forensic systems.

This dual implementation allows direct comparison between a conventional Ethereum deployment and a modern Layer-2 architecture, making the repository valuable for both software development and blockchain research.

---

# Key Features

zkChainSEAL combines blockchain technology, decentralized storage, and modern web technologies to provide a secure and transparent platform for digital evidence management. The system is designed to ensure evidence integrity while remaining scalable, cost-efficient, and easy to extend.


## Core Features

### Blockchain-Based Evidence Registration

Every piece of digital evidence is registered on the blockchain through Ethereum-compatible smart contracts. Instead of relying on centralized records, the blockchain acts as an immutable ledger that permanently records evidence metadata and cryptographic hashes.


### Tamper-Evident Integrity Verification

Each evidence file is processed using cryptographic hashing before registration. During verification, the evidence is hashed again and compared with the immutable blockchain record, allowing any modification to be detected immediately.


### Decentralized Evidence Storage

Evidence files are stored using the **InterPlanetary File System (IPFS)** rather than directly on the blockchain. This approach provides content-addressable storage while significantly reducing blockchain storage costs and improving scalability.


### Evidence Lifecycle Management

The platform supports the complete lifecycle of digital evidence, including:

- Evidence registration
- Secure storage
- Metadata management
- Integrity verification
- Retrieval by authorized users


## Security Features

### Immutable Audit Trail

Every blockchain transaction creates a permanent and chronological record of evidence-related operations, providing an auditable chain of custody throughout the investigation process.


### Role-Based Access Control (RBAC)

Smart contracts enforce role-based permissions to ensure that only authorized users can perform sensitive operations such as evidence registration and management.

Examples of supported roles include:

- Administrator
- Investigator
- Forensic Officer
- Authorized Personnel


### Wallet-Based Authentication

User authentication is performed through **MetaMask**, eliminating traditional password-based authentication and enabling blockchain-native identity verification.


### Secure Configuration Management

Sensitive credentials are managed through environment variables instead of hardcoded values. The repository includes `.env.example` templates while excluding actual configuration files from version control.


## Blockchain Features

### Ethereum Compatibility

The platform is fully compatible with Ethereum Virtual Machine (EVM) networks, enabling deployment on Ethereum Sepolia as well as Layer-2 networks such as zkSync Era.


### zkSync Era Integration

The project extends the original Ethereum implementation by integrating **zkSync Era**, enabling:

- Lower transaction costs
- Higher transaction throughput
- Faster confirmations
- Improved scalability

while preserving compatibility with existing Ethereum smart contracts.


### Smart Contract Automation

Business logic related to evidence registration, verification, and authorization is implemented within Solidity smart contracts, ensuring consistent and transparent execution.


### Cryptographic Verification

The platform relies on cryptographic hash functions to generate unique fingerprints for every evidence file, enabling deterministic integrity verification without exposing the original data on-chain.


## Developer Features

### Modern Technology Stack

The project is built using a modern and widely adopted development stack:

- React
- TypeScript
- Solidity
- Foundry
- Node.js
- Express
- Supabase
- IPFS


### Modular Architecture

The repository follows a modular structure that separates:

- Frontend application
- Backend services
- Smart contracts
- Deployment scripts
- Configuration

This organization simplifies maintenance and encourages future extensions.


### Open-Source Development

The project follows standard open-source development practices, including:

- MIT License
- Contribution Guidelines
- Code of Conduct
- Security Policy
- Environment Variable Templates

making it easy for new contributors to participate.


## Research Contributions

Beyond serving as a software application, zkChainSEAL provides a practical platform for exploring blockchain-based digital evidence management. The repository enables experimentation with:

- Blockchain-backed chain of custody
- Secure evidence verification
- Ethereum Layer-2 scalability
- Decentralized storage architectures
- Smart contract-based authorization
- Future integration of Zero-Knowledge Proofs (ZKPs)

These capabilities make the project suitable for academic research, prototype development, and further exploration of blockchain applications in digital forensics.

---

# System Architecture

zkChainSEAL follows a modular, layered architecture that separates the user interface, backend services, blockchain logic, decentralized storage, and metadata management. This separation improves maintainability, scalability, and simplifies future extensions while ensuring that each component has a well-defined responsibility.

The overall system architecture is illustrated below.

```text
                              +----------------------+
                              |        User          |
                              +----------+-----------+
                                         |
                                         |
                                         ▼
                     +---------------------------------------+
                     | React + TypeScript Frontend           |
                     | - Dashboard                           |
                     | - Evidence Management                 |
                     | - MetaMask Authentication             |
                     +----------------+----------------------+
                                      |
                                      |
                    REST API          |          Web3 Calls
                                      |
                 +--------------------+--------------------+
                 |                                         |
                 ▼                                         ▼
      +------------------------+              +----------------------------+
      | Node.js Backend        |              | Smart Contracts            |
      | Express API            |              | Solidity                   |
      | Business Logic         |              | Role Management            |
      | IPFS Integration       |              | Evidence Registration      |
      +-----------+------------+              | Verification               |
                  |                           +-------------+--------------+
                  |                                         |
                  ▼                                         ▼
        +--------------------+                 +--------------------------+
        |      Supabase      |                 | Ethereum / zkSync Era    |
        | Metadata Storage   |                 | Immutable Ledger         |
        +--------------------+                 +--------------------------+
                  ^
                  |
                  |
                  ▼
          +--------------------+
          |        IPFS        |
          | Evidence Storage   |
          +--------------------+
```


# Architecture Components

## 1. Frontend Layer

The frontend provides the primary interface through which investigators and authorized users interact with the system.

Built using **React** and **TypeScript**, it offers a responsive and modern interface for managing digital evidence while communicating with both blockchain and backend services.

Its primary responsibilities include:

- MetaMask wallet connection
- User authentication
- Evidence submission
- Evidence verification
- FIR management
- Viewing blockchain transaction status
- Displaying evidence metadata

The frontend never stores sensitive blockchain credentials or private keys.


## 2. Backend Layer

The backend is implemented using **Node.js** and **Express**.

Unlike the blockchain layer, the backend manages operations that are better suited for traditional server-side processing.

Responsibilities include:

- Uploading evidence to IPFS
- Retrieving evidence files
- Managing metadata
- Coordinating frontend requests
- Communicating with Supabase
- Preparing data before blockchain registration

Keeping these responsibilities off-chain reduces gas costs while maintaining flexibility.


## 3. Smart Contract Layer

The Solidity smart contracts form the trust layer of zkChainSEAL.

They are responsible for enforcing security policies and maintaining an immutable record of evidence operations.

Major responsibilities include:

- Registering evidence hashes
- Managing user roles
- Recording blockchain events
- Preventing unauthorized operations
- Maintaining immutable evidence records

Since blockchain data cannot be modified after confirmation, the smart contracts provide strong guarantees regarding evidence integrity.


## 4. Blockchain Layer

The blockchain acts as the immutable source of truth for evidence registration.

Rather than storing evidence itself, it stores:

- Cryptographic evidence hashes
- Evidence identifiers
- Ownership information
- Transaction history
- Registration timestamps

The project currently supports:

- Ethereum Sepolia
- zkSync Era Sepolia

allowing direct comparison between Layer-1 and Layer-2 deployments.


## 5. IPFS Storage Layer

Digital evidence files such as documents, images, videos, and forensic artifacts are stored in the **InterPlanetary File System (IPFS)**.

Each uploaded file generates a unique **Content Identifier (CID)**, which can later be used to retrieve the exact file.

Benefits include:

- Decentralized storage
- Content-addressable retrieval
- Reduced blockchain storage costs
- Efficient handling of large files

Only the CID and corresponding evidence hash are associated with blockchain records.


## 6. Metadata Layer

Operational metadata is stored in **Supabase**.

Examples include:

- FIR details
- Case information
- User information
- Investigation metadata
- IPFS references
- Application state

Since this information changes more frequently than blockchain records, storing it in a database provides significantly better performance and flexibility.


## Data Flow

The following sequence summarizes how evidence moves through the system.

```text
Evidence Collected
        │
        ▼
User uploads evidence
        │
        ▼
Backend receives file
        │
        ▼
Evidence uploaded to IPFS
        │
        ▼
CID returned
        │
        ▼
SHA-256 hash generated
        │
        ▼
Hash submitted to Smart Contract
        │
        ▼
Blockchain transaction confirmed
        │
        ▼
Metadata stored in Supabase
        │
        ▼
Evidence successfully registered
```


## Technology Stack

| Layer | Technology | Purpose |
|--------|------------|---------|
| Frontend | React + TypeScript | User Interface |
| Backend | Node.js + Express | Business Logic |
| Smart Contracts | Solidity | On-chain Logic |
| Development Framework | Foundry | Smart Contract Development |
| Wallet | MetaMask | User Authentication |
| Blockchain | Ethereum Sepolia | Baseline Implementation |
| Layer-2 | zkSync Era | Scalable Deployment |
| Storage | IPFS + Pinata | Evidence Storage |
| Database | Supabase | Metadata Management |


## Design Decisions

The architecture of zkChainSEAL was guided by practical trade-offs between security, scalability, performance, and development simplicity.

### Why store only hashes on-chain?

Storing complete evidence files on the blockchain is prohibitively expensive and unnecessary for integrity verification. Recording only cryptographic hashes provides tamper detection while keeping transaction costs low.


### Why use IPFS?

IPFS enables decentralized, content-addressable storage for large digital files. It complements blockchain by handling storage efficiently while preserving data integrity through immutable content identifiers.


### Why use Supabase?

Metadata such as FIR information, user profiles, and application state changes frequently. A relational database provides faster querying and easier management than storing such data on-chain.


### Why migrate to zkSync Era?

Ethereum provides strong security guarantees but can become costly for frequent transactions. zkSync Era significantly reduces gas fees and improves throughput while remaining fully compatible with Ethereum smart contracts.


### Why Foundry?

Foundry provides a modern Solidity development environment with fast compilation, efficient testing, scripting capabilities, and seamless deployment support.


## Repository Structure

```text
zkChainSEAL/
│
├── contracts/             # Solidity smart contracts
├── script/                # Deployment scripts
├── test/                  # Smart contract tests
├── src/                   # React frontend
├── public/                # Static frontend assets
├── ipfs-backend/          # Express backend and IPFS integration
├── lib/                   # External Solidity libraries
├── .env.example
├── foundry.toml
├── package.json
├── README.md
└── LICENSE
```


## Branch Strategy

The repository follows a two-branch development strategy.

| Branch | Purpose |
|---------|---------|
| **zksync-integration** | Primary development branch containing the latest features and zkSync Era implementation. |
| **ethereum-baseline** | Stable Ethereum implementation maintained for comparison and reference. |

This strategy enables experimentation with Layer-2 technologies while preserving a clean Ethereum baseline for benchmarking and future research.

---

# Getting Started

This guide will help you set up zkChainSEAL locally for development and testing.


## Prerequisites

Before you begin, ensure the following software is installed on your system.

| Software | Version |
|-----------|---------|
| Node.js | 18 or later |
| npm | Latest |
| Git | Latest |
| Foundry | Latest Stable |
| MetaMask | Browser Extension |


You should also have access to:

- An Ethereum Sepolia RPC endpoint
- A zkSync Era Sepolia RPC endpoint
- A Pinata account (for IPFS uploads)
- A Supabase project
- A wallet funded with Sepolia ETH (or zkSync Era testnet ETH)


## Clone the Repository

```bash
git clone https://github.com/karanaggarwal01/zkChainSEAL.git

cd zkChainSEAL
```


## Install Dependencies

Install frontend dependencies.

```bash
npm install
```

Install backend dependencies.

```bash
cd ipfs-backend

npm install

cd ..
```

Install Solidity dependencies.

```bash
forge install
```

Compile smart contracts.

```bash
forge build
```


## Environment Configuration

The project uses environment variables for all sensitive configuration.

Never commit actual `.env` files to version control.


### Frontend Environment

Create a `.env` file in the project root.

```bash
cp .env.example .env
```

Example:

```env
VITE_SUPABASE_URL=
VITE_SUPABASE_ANON_KEY=
VITE_CONTRACT_ADDRESS=
VITE_CHAIN_ID=
```


### Backend Environment

Create another `.env` inside the `ipfs-backend` directory.

```bash
cp ipfs-backend/.env.example ipfs-backend/.env
```

Example:

```env
PINATA_JWT=
PINATA_GATEWAY=
SUPABASE_URL=
SUPABASE_KEY=
PRIVATE_KEY=
RPC_URL=
CONTRACT_ADDRESS=
```

> **Important**
>
> Never expose private keys, API tokens, or service credentials. The provided `.env.example` files should be used as templates only.


## Running the Application

### Start the Frontend

```bash
npm run dev
```

The React application will be available at:

```
http://localhost:5173
```


### Start the Backend

Open another terminal.

```bash
cd ipfs-backend

node backendfinal.js
```

The backend will start at:

```
http://localhost:4000
```


### Smart Contract Development

Compile contracts.

```bash
forge build
```

Run tests.

```bash
forge test
```

Generate gas report.

```bash
forge test --gas-report
```

Format Solidity files.

```bash
forge fmt
```

Clean build artifacts.

```bash
forge clean
```


### MetaMask Configuration

Connect MetaMask to the appropriate test network.

Supported networks include:

- Ethereum Sepolia
- zkSync Era Sepolia

Ensure the connected wallet:

- Has sufficient test ETH
- Is connected to the correct network
- Matches the configured contract deployment


## Project Structure After Setup

Once everything is configured, your local workspace should resemble the following.

```text
zkChainSEAL/
│
├── contracts/
├── script/
├── test/
├── src/
├── public/
├── ipfs-backend/
│   ├── backendfinal.js
│   ├── package.json
│   └── .env
│
├── .env
├── package.json
├── foundry.toml
└── README.md
```


## Verification Checklist

Before using the application, verify the following:

- Node.js dependencies are installed.
- Backend dependencies are installed.
- Smart contracts compile successfully.
- MetaMask is connected.
- Environment variables are configured.
- Backend is running.
- Frontend loads successfully.
- Wallet connection works.
- Evidence uploads to IPFS.
- Blockchain transactions are confirmed.


## Common Development Commands

| Command | Description |
|----------|-------------|
| `npm run dev` | Start React development server |
| `npm run build` | Build frontend for production |
| `forge build` | Compile smart contracts |
| `forge test` | Execute contract tests |
| `forge fmt` | Format Solidity source code |
| `forge clean` | Remove build artifacts |
| `node backendfinal.js` | Start backend server |


## Troubleshooting

### MetaMask cannot connect

- Ensure MetaMask is installed.
- Verify the selected network.
- Confirm the wallet is unlocked.
- Check that the contract address matches the deployed network.


### IPFS upload fails

- Verify your Pinata credentials.
- Ensure the backend server is running.
- Confirm the JWT token is valid.


### Smart contracts fail to compile

Run:

```bash
forge clean

forge install

forge build
```


### Backend cannot start

Verify:

- `.env` exists inside `ipfs-backend`
- RPC endpoint is reachable
- Contract address is correct
- Required API keys are configured


### Frontend cannot communicate with backend

Confirm:

- Backend is running on the expected port.
- Frontend environment variables are configured correctly.
- API endpoints match the backend configuration.
- Browser console does not show network or CORS errors.

---

# Technical Overview

This section provides an overview of the core blockchain components, security mechanisms, and evidence processing workflow implemented in zkChainSEAL.


## Smart Contract Architecture

The smart contracts serve as the trust layer of the application. They maintain immutable evidence records, enforce authorization rules, and provide cryptographically verifiable evidence registration.

Unlike conventional applications where the backend owns the source of truth, zkChainSEAL treats the blockchain as the authoritative ledger for evidence integrity.

The contracts are responsible for:

- Registering new evidence records
- Maintaining immutable evidence hashes
- Enforcing role-based permissions
- Recording blockchain events
- Verifying evidence integrity
- Maintaining an auditable chain of custody

Every successful registration produces an on-chain transaction that becomes part of the permanent blockchain history.


## Smart Contract Responsibilities

| Component | Responsibility |
|-----------|----------------|
| Evidence Registry | Registers evidence hashes and metadata references |
| Access Control | Manages user roles and permissions |
| Verification Logic | Validates evidence integrity using cryptographic hashes |
| Event Logging | Emits blockchain events for auditing and traceability |


## Security Model

Security is a primary design goal of zkChainSEAL. Rather than relying on a single trusted authority, the platform combines blockchain immutability, cryptographic hashing, decentralized storage, and wallet-based authentication to strengthen the integrity and transparency of digital evidence management.

### Role-Based Access Control

Access to sensitive operations is governed by smart contracts.

Typical roles include:

- Administrator
- Investigator
- Forensic Officer
- Authorized Personnel

Only users with the appropriate permissions can perform operations such as evidence registration or management.


### Wallet Authentication

The platform uses **MetaMask** for authentication.

Instead of usernames and passwords, users authenticate by signing blockchain transactions with their wallet. This approach eliminates password storage while providing cryptographic proof of identity.


### Evidence Integrity

Every uploaded evidence file is processed to generate a cryptographic hash.

The generated hash is stored permanently on the blockchain, while the original evidence remains in IPFS.

During verification:

1. The evidence is retrieved.
2. A new hash is generated.
3. The newly generated hash is compared with the blockchain record.

If both hashes match, the evidence has remained unchanged since registration.


### Immutable Audit Trail

Every blockchain transaction contributes to a permanent audit trail containing:

- Registration timestamps
- Transaction identifiers
- Authorized user actions
- Evidence updates
- Verification events

Because blockchain records cannot be modified retrospectively, the audit trail provides strong evidence of system activity over time.


### Secure Secret Management

Sensitive configuration values such as API keys, private keys, and service credentials are never committed to version control.

The project uses:

- `.env`
- `.env.example`

to separate local configuration from the public repository.


## Evidence Lifecycle

The following workflow summarizes how digital evidence moves through the system.

```text
Evidence Collection
        │
        ▼
Evidence Upload
        │
        ▼
SHA-256 Hash Generation
        │
        ▼
IPFS Upload
        │
        ▼
Content Identifier (CID)
        │
        ▼
Blockchain Registration
        │
        ▼
Metadata Storage
        │
        ▼
Evidence Verification
        │
        ▼
Integrity Confirmation
```

Each stage is designed to ensure that evidence remains authentic, traceable, and independently verifiable throughout its lifecycle.


## Contributing

Contributions are welcome and greatly appreciated.

Whether you are fixing bugs, improving documentation, optimizing smart contracts, or proposing new research ideas, your contributions help improve the project.

Please review the following documents before contributing:

- `CONTRIBUTING.md`
- `SECURITY.md`
- `CODE_OF_CONDUCT.md`

### Contribution Workflow

1. Fork the repository.
2. Create a feature branch.
3. Commit your changes with descriptive commit messages.
4. Ensure all tests pass.
5. Open a Pull Request.
6. Participate in the review process.


## Current Limitations

zkChainSEAL is currently an active research prototype and has several known limitations.

- Designed primarily for testnet deployment.
- Smart contracts have not undergone an independent security audit.
- IPFS availability depends on configured pinning services.
- Limited benchmarking under high transaction volumes.
- Current implementation focuses on evidence registration and verification rather than complete judicial workflows.

These limitations provide opportunities for future development and research.


## Future Roadmap

The project will continue evolving with new features and research directions, including:

### Scalability

- Enhanced zkSync Era integration
- Transaction cost optimization
- Batch evidence registration

### Security

- Zero-Knowledge Proof (ZKP) integration
- Advanced cryptographic verification
- Smart contract security audits

### Functionality

- Multi-chain compatibility
- Enhanced evidence search
- Improved case management
- Better user experience
- Advanced analytics and dashboards

### Research

- Performance evaluation across Layer-1 and Layer-2 networks
- Comparative gas cost analysis
- Scalability benchmarking
- Integration of emerging blockchain technologies


## Research Context

zkChainSEAL is an open-source research prototype developed to explore the application of blockchain technology in digital evidence management.

The project investigates how Ethereum-compatible smart contracts, decentralized storage, and Layer-2 scaling solutions can improve the integrity, transparency, and scalability of digital forensic workflows.

The repository is intended to support:

- Academic research
- Blockchain experimentation
- Educational purposes
- Open-source collaboration
- Future extensions in digital forensics

---

# License

This project is licensed under the **MIT License**.

See the [LICENSE](LICENSE) file for complete licensing information.

---

# Contact

**Karan Aggarwal**

If you have questions, suggestions, or would like to contribute, feel free to open an issue or submit a pull request.

- **GitHub:** https://github.com/karanaggarwal01