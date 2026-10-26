# Security Policy

## Zero-Knowledge Architecture

SyncAll is designed with a **Zero-Knowledge** security posture:
- **Client-Side Encryption**: Files can be encrypted locally using AES-256-CBC with an HMAC-SHA256 authentication envelope before transmission to any cloud provider.
- **Constant Memory Footprint**: Streaming chunk IO ensures encryption keys and file buffers are processed with $O(1)$ memory usage.
- **Path Obfuscation**: Real directory and file names can be obfuscated on the cloud with cryptographic identifiers.
- **Local Key Storage**: Master keys are never transmitted to any third-party server and remain under full user custody.

## Reporting a Vulnerability

If you discover a security vulnerability within SyncAll or its distribution pipelines:

1. **Do not create a public issue.**
2. Send a detailed vulnerability report privately to the maintainers or open a [Private Vulnerability Advisory](https://github.com/priyaranjan-sahu/syncall-community/security/advisories/new).
3. Include reproduction steps, environment details, and proof of concept.

Maintainers will respond within 48 hours to validate and address the issue.
