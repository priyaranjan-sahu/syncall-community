# SyncAll Community ☁️⚡

[![Automated Multi-Platform Testing](https://github.com/priyaranjan-sahu/syncall-community/actions/workflows/test.yml/badge.svg)](https://github.com/priyaranjan-sahu/syncall-community/actions/workflows/test.yml)
[![Cross-Platform Multi-Cloud Build Pipeline](https://github.com/priyaranjan-sahu/syncall-community/actions/workflows/builder.yml/badge.svg)](https://github.com/priyaranjan-sahu/syncall-community/actions/workflows/builder.yml)
[![Public Repo Source Guard](https://github.com/priyaranjan-sahu/syncall-community/actions/workflows/no-source-guard.yml/badge.svg)](https://github.com/priyaranjan-sahu/syncall-community/actions/workflows/no-source-guard.yml)
[![Security: Zero-Knowledge AES-256](https://img.shields.io/badge/Security-Zero--Knowledge%20AES--256-00E5FF?style=flat&logo=shield)](SECURITY.md)
[![Platforms](https://img.shields.io/badge/Platforms-Windows%20%7C%20Linux%20%7C%20macOS%20%7C%20Android%20%7C%20Web-blue)](https://github.com/priyaranjan-sahu/syncall-community/releases)

**SyncAll** is an enterprise-grade, zero-knowledge, cross-platform file synchronization application that seamlessly unifies **Google Drive, Microsoft OneDrive, Dropbox, MEGA, AWS S3 / Cloudflare R2 / MinIO, and Local/NAS volumes**.

This repository (`syncall-community`) is the **public distribution portal and CI/CD runner repository** for SyncAll. It securely hosts automated testing, multi-platform artifact builds, release pipelines, and user documentation without exposing the proprietary core codebase.

---

## 🚀 Triggering Workflows Manually with Specific Branches

You can trigger the workflows manually from the **Actions** tab on this repository. Each workflow provides a `branch` input allowing you to test or build any branch or tag from the private repository (`priyaranjan-sahu/syncall`).

### 1. From the GitHub Web Interface
1. Go to [**Actions**](https://github.com/priyaranjan-sahu/syncall-community/actions).
2. Select either:
   - **[Automated Multi-Platform Testing](https://github.com/priyaranjan-sahu/syncall-community/actions/workflows/test.yml)** (runs Ubuntu, Windows, macOS test matrix)
   - **[Cross-Platform Multi-Cloud Build Pipeline](https://github.com/priyaranjan-sahu/syncall-community/actions/workflows/builder.yml)** (compiles Windows, Linux, Android, Web, and macOS binaries)
3. Click the **Run workflow** dropdown on the right.
4. In the **Branch or Tag from private repo** input box:
   - Enter your target branch name (e.g. `main`, `dev`, `feature/mesh-topology`, `fix/login`, or a release tag like `v1.0.0`).
5. Click the green **Run workflow** button.

---

### 2. From the GitHub CLI (`gh`)

#### Run the Multi-Platform Test Suite against a specific branch:
```bash
# Test 'main' branch
gh workflow run test.yml --repo priyaranjan-sahu/syncall-community -f branch=main

# Test any feature branch
gh workflow run test.yml --repo priyaranjan-sahu/syncall-community -f branch=feature/mesh-topology
```

#### Run the Cross-Platform Build Pipeline from a specific branch:
```bash
# Build release artifacts from 'main'
gh workflow run builder.yml --repo priyaranjan-sahu/syncall-community \
  -f branch=main \
  -f version=1.0.0 \
  -f create_release=true

# Build test artifacts from a development branch without publishing
gh workflow run builder.yml --repo priyaranjan-sahu/syncall-community \
  -f branch=dev \
  -f version=1.0.0-dev \
  -f create_release=false
```

---

## 📦 Downloads & Releases

Pre-compiled binary releases for all major desktop and mobile operating systems are published under [**Releases**](https://github.com/priyaranjan-sahu/syncall-community/releases):

| Platform | Package | Architecture | Verification |
|---|---|---|---|
| **Windows** | `SyncAll-v*-Windows-x64.zip` | 64-bit Intel/AMD | SHA-256 in `SHA256SUMS.txt` |
| **Linux** | `SyncAll-v*-Linux-x64.tar.gz` | x86_64 (GTK-3) | SHA-256 in `SHA256SUMS.txt` |
| **macOS** | `SyncAll-v*-macOS.zip` | Universal (Apple Silicon & Intel) | SHA-256 in `SHA256SUMS.txt` |
| **Android** | `SyncAll-v*-Android.apk` | ARM64 / ARMv7 | SHA-256 in `SHA256SUMS.txt` |
| **Web** | `SyncAll-v*-Web.zip` | Progressive Web App | SHA-256 in `SHA256SUMS.txt` |

---

## 🔒 Security & Source Code Protection

To guarantee that proprietary application source code remains private:

1. **Zero Source Code Leaks**: The [Public Repo Source Guard](.github/workflows/no-source-guard.yml) workflow verifies on every push that no application code (`lib/`, `android/`, `ios/`, `windows/`, `.env`, keys) is ever committed to this public repository.
2. **Ephemeral In-Memory Runner Checkout**: Workflows check out the private source into an isolated, ephemeral GitHub-hosted runner environment using secure access tokens (`PRIVATE_REPO_TOKEN`). Source code exists in the runner memory only for the duration of the test/build job and is destroyed upon container termination.
3. **Reproducible Checksums**: Every release publishes cryptographic SHA-256 hashes for binary transparency and integrity verification.

---

## 📜 License & Compliance

Distribution packages are licensed for personal and community use. See [SECURITY.md](SECURITY.md) for vulnerability disclosure procedures.
