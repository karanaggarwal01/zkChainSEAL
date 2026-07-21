# Contributing to zkChainSEAL

First of all, thank you for considering contributing to **zkChainSEAL**! 🚀

zkChainSEAL is a blockchain-based digital evidence management system built using Ethereum, zkSync Era, IPFS, React, Solidity, and Supabase. Contributions that improve security, scalability, documentation, performance, or developer experience are always welcome.

---

# Table of Contents

- Code of Conduct
- Project Structure
- Development Workflow
- Getting Started
- Setting Up the Development Environment
- Branching Strategy
- Coding Standards
- Testing Guidelines
- Commit Message Guidelines
- Pull Request Guidelines
- Security Guidelines
- Documentation
- Getting Help

---

# Code of Conduct

Please read and follow our [Code of Conduct](CODE_OF_CONDUCT.md) before contributing.

We aim to maintain a welcoming, respectful, and collaborative environment.

---

# Project Structure

The repository currently contains two primary branches.

## ethereum-baseline

Reference implementation built on Ethereum.

This branch is maintained as a stable baseline and generally only receives maintenance updates.

---

## zksync-integration (Default Branch)

This is the active development branch.

It contains:

- zkSync Era integration
- MetaMask authentication improvements
- IPFS integration
- Security improvements
- Active feature development

Unless you're fixing an issue specific to the Ethereum baseline, all new work should target this branch.

---

# Getting Started

## Prerequisites

- Node.js 18+
- npm
- Git
- Foundry
- MetaMask
- Basic knowledge of:
  - React
  - TypeScript
  - Solidity
  - Ethereum
  - zkSync Era
  - IPFS

---

# Development Setup

Clone the repository

```bash
git clone https://github.com/karanaggarwal01/zkChainSEAL.git
cd zkChainSEAL
```

Install frontend dependencies

```bash
npm install
```

Install backend dependencies

```bash
cd ipfs-backend
npm install
cd ..
```

Install Foundry

```bash
curl -L https://foundry.paradigm.xyz | bash
foundryup
```

---

# Environment Variables

Copy the example environment files.

```bash
cp .env.example .env
cp ipfs-backend/.env.example ipfs-backend/.env
```

Fill in the required values.

Example:

```
SUPABASE_URL=
SUPABASE_KEY=
PINATA_JWT=
PINATA_GATEWAY=
PRIVATE_KEY=
RPC_URL=
```

⚠️ Never commit `.env` files or secrets.

---

# Branching Strategy

Always create new branches from:

```
zksync-integration
```

Example:

```bash
git checkout zksync-integration
git pull
git checkout -b feature/feature-name
```

Suggested branch names

```
feature/evidence-search
feature/zk-proof
fix/ipfs-upload
docs/readme
refactor/backend
test/contracts
```

---

# Commit Guidelines

Write clear commit messages.

Examples:

```
feat(ipfs): add evidence metadata upload

fix(auth): resolve MetaMask reconnect issue

docs: update installation guide

refactor(contract): optimize access control
```

Avoid vague commit messages like:

```
fixed stuff
changes
update
```

---

# Coding Standards

## Frontend

- Use TypeScript
- Prefer functional React components
- Use hooks
- Keep components modular
- Follow ESLint rules

---

## Smart Contracts

- Follow Solidity style guide
- Use descriptive custom errors
- Emit events for state changes
- Keep functions small
- Document public functions

---

## Backend

- Validate inputs
- Handle errors gracefully
- Never hardcode secrets
- Use environment variables
- Log meaningful errors

---

# Testing

Before opening a Pull Request:

Frontend

- Application builds successfully
- No console errors
- UI tested manually

Smart Contracts

- All Foundry tests pass
- Deployment scripts execute successfully
- Gas usage reviewed where appropriate

Backend

- API endpoints tested
- IPFS uploads verified
- Supabase integration verified

---

# Pull Requests

Please ensure:

- Code builds successfully
- Documentation updated if necessary
- No secrets committed
- Meaningful commit history
- PR description explains the motivation
- Screenshots included for UI changes

---

# Security Guidelines

Never commit:

- `.env`
- Private keys
- Wallet mnemonics
- Supabase service keys
- Pinata JWTs
- API tokens

Always use environment variables.

If you discover a security issue, please follow the instructions in `SECURITY.md`.

---

# Documentation

Documentation improvements are always appreciated.

When introducing new features, please update:

- README
- Architecture diagrams (if needed)
- Setup instructions
- API documentation (if applicable)

---

# Getting Help

If you have questions:

- Open a GitHub Discussion (if enabled)
- Create an Issue
- Contact the maintainer through GitHub

---

Thank you for contributing to zkChainSEAL!

Every contribution, whether it's code, documentation, bug reports, or ideas, helps improve the project.
