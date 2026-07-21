# Security Policy

Security is an important aspect of zkChainSEAL. Since this project deals with blockchain-based evidence management, protecting secrets, ensuring integrity, and following secure development practices are essential.

---

# Supported Branches

| Branch | Status |
|---------|--------|
| zksync-integration | ✅ Active Development |
| ethereum-baseline | ✅ Maintenance Only |

Security fixes are primarily applied to the active development branch.

---

# Reporting a Vulnerability

Please **DO NOT** create public GitHub issues for security vulnerabilities.

Instead, report vulnerabilities privately by:

- Opening a GitHub Security Advisory (preferred)
- Contacting the maintainer through GitHub

Please include:

- Description
- Steps to reproduce
- Potential impact
- Suggested mitigation (if known)

---

# Response Policy

Target response times:

| Severity | Initial Response |
|------------|----------------|
| Critical | Within 48 hours |
| High | Within 5 days |
| Medium | Within 7 days |
| Low | Best effort |

---

# Security Best Practices

## Secrets

Never commit:

- `.env`
- Private keys
- Wallet mnemonics
- Pinata JWTs
- Supabase service keys
- API keys
- RPC credentials

All sensitive information should be stored using environment variables.

---

## Smart Contracts

Current security measures include:

- Role-based access control
- Immutable evidence records
- Event logging
- Evidence hash verification
- Controlled state transitions

Future improvements include:

- External smart contract audits
- Formal verification
- Zero-Knowledge proof integration

---

## Backend Security

The backend should:

- Validate all user input
- Handle errors safely
- Never expose internal exceptions
- Use secure environment variables
- Limit access to privileged operations

---

## Frontend Security

- Never store secrets in frontend code.
- Always verify connected wallet information.
- Validate user inputs before submission.
- Keep dependencies updated.

---

## IPFS Security

Evidence files are stored using IPFS.

Security considerations include:

- Content-addressable storage
- Hash verification
- Immutable content identifiers

Sensitive files should be encrypted before permanent decentralized storage if confidentiality is required.

---

## Wallet Security

Developers and users should:

- Use separate wallets for development and production
- Never share private keys
- Keep seed phrases offline
- Verify transactions before signing
- Prefer hardware wallets for production deployments

---

# Current Limitations

This project is intended for research and educational purposes.

Current limitations include:

- No formal third-party smart contract audit
- No production security certification
- Testnet deployment only
- Experimental zkSync integration

Do not deploy this project to production environments handling sensitive real-world evidence without a comprehensive security review.

---

# Dependency Security

Before opening a Pull Request:

Run:

```bash
npm audit
```

and

```bash
forge test
```

Address critical dependency vulnerabilities whenever possible.

---

# Responsible Disclosure

We follow responsible disclosure practices.

The general process is:

1. Vulnerability reported privately
2. Issue reproduced
3. Fix developed
4. Security update released
5. Public disclosure (if appropriate)

---

# Security Recommendations

Developers should:

- Keep dependencies updated
- Review smart contract changes carefully
- Follow secure coding practices
- Avoid committing sensitive information
- Perform regular code reviews

---

Thank you for helping improve the security of zkChainSEAL.