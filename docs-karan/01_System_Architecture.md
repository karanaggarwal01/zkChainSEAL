# ChainSEAL Architecture Documentation

## Project Overview

ChainSEAL is a blockchain-based digital forensic evidence management system.

The project combines:

- Ethereum Smart Contracts
- IPFS
- Pinata
- Supabase
- React
- Express Backend
- MetaMask

The architecture is hybrid.

Blockchain stores immutable forensic records.

IPFS stores evidence files.

Supabase stores application metadata.

---

## High-Level Architecture

User

↓

React Frontend

↓

MetaMask

↓

Ethereum Smart Contract

↓

IPFS Backend

↓

Pinata/IPFS

↓

Supabase

---

## Major Components

### Frontend

Framework:
React + TypeScript + Vite

Responsibilities

- Login
- Dashboard
- FIR Management
- Case Management
- Evidence Upload
- Role Management

---

### Backend

Node.js + Express

Responsibilities

- Encrypt evidence
- Upload to Pinata
- Submit blockchain transactions
- Retrieve IPFS files

---

### Blockchain

Ethereum Sepolia

Responsibilities

- Role management
- FIR registration
- Case management
- Evidence integrity
- Chain of custody

---

### Database

Supabase

Responsibilities

- User profiles
- Role assignments
- FIR metadata
- Case metadata
- Evidence metadata

---

### Storage

IPFS

Responsibilities

- Original evidence
- Encrypted evidence
- Long-term storage
