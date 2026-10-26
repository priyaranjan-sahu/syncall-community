# SyncAll Community ☁️⚡

[![Automated Multi-Platform Testing](https://github.com/priyaranjan-sahu/syncall-community/actions/workflows/test.yml/badge.svg)](https://github.com/priyaranjan-sahu/syncall-community/actions/workflows/test.yml)
[![Cross-Platform Multi-Cloud Build Pipeline](https://github.com/priyaranjan-sahu/syncall-community/actions/workflows/builder.yml/badge.svg)](https://github.com/priyaranjan-sahu/syncall-community/actions/workflows/builder.yml)
[![Public Repo Source Guard](https://github.com/priyaranjan-sahu/syncall-community/actions/workflows/no-source-guard.yml/badge.svg)](https://github.com/priyaranjan-sahu/syncall-community/actions/workflows/no-source-guard.yml)
[![Security: Zero-Knowledge AES-256](https://img.shields.io/badge/Security-Zero--Knowledge%20AES--256-00E5FF?style=flat&logo=shield)](SECURITY.md)
[![Platforms](https://img.shields.io/badge/Platforms-Windows%20%7C%20Linux%20%7C%20macOS%20%7C%20Android%20%7C%20Web-blue)](https://github.com/priyaranjan-sahu/syncall-community/releases)

**SyncAll** is an enterprise-grade, zero-knowledge, cross-platform file synchronization application that seamlessly unifies **Google Drive, Microsoft OneDrive, Dropbox, MEGA, AWS S3 / Cloudflare R2 / MinIO, and Local/NAS volumes**.

This repository (`syncall-community`) is the **public distribution portal and CI/CD runner repository** for SyncAll. It securely hosts automated testing, multi-platform artifact builds, release pipelines, and user documentation without exposing the proprietary core codebase.

---

## 🚀 Key Features

- ☁️ **Universal Multi-Cloud Support**: Google Drive, Microsoft OneDrive, Dropbox, MEGA, and AWS S3-compatible object stores (AWS, Cloudflare R2, MinIO, Wasabi, Backblaze B2).
- 🌐 **Live Mesh Topology Visualizer**: Real-time interactive node canvas mapping latency telemetry, connection health, and glowing data packets across all connected drives.
- 🗄️ **Virtual Super-Drive (RAID-Cloud)**: Aggregates disparate cloud quotas into a single unified storage pool with simulated AI block sharding.
- 🔐 **Zero-Knowledge Client-Side Encryption**: True $O(1)$ memory streaming AES-256-CBC encryption with HMAC-SHA256 authenticated envelopes before file transmission.
- ⚡ **3-Way Snapshot Synchronization**: Baseline snapshot database and offline tombstones ensure accurate bidirectional and unidirectional reconciliation without data loss.
- ⏱️ **AI Smart Sync & Bandwidth Autopilot**: Dynamic concurrency modes (*Ultra Velocity*, *Adaptive Balanced*, *Stealth Silent*) with metered network auto-pausing.
- 🛡️ **Quantum Air-Gap Killswitch**: Instant severance of all in-flight network sockets and memory key scrubbing on detected anomalous activity.
- ⌨️ **Universal Command Palette (`Ctrl+K` / `Cmd+K`)**: Rapid desktop navigation, immediate rule sync, and non-destructive dry-run simulations.

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

## 🛠️ GitHub Actions Runner Pipelines

### 1. [Automated Multi-Platform Testing](.github/workflows/test.yml)
Runs the test suite across Ubuntu Linux, Windows, and macOS:
- Full compilation check across platforms
- Static analysis via `flutter analyze`
- 43+ unit and widget tests
- Code coverage reporting

### 2. [Cross-Platform Multi-Cloud Build Pipeline](.github/workflows/builder.yml)
Compiles production-ready release bundles:
- Windows desktop executable (`.zip`)
- Linux desktop standalone binary (`.tar.gz`)
- Android release APK (`.apk`)
- Web production bundle (`.zip`)
- macOS desktop application (`.zip`)
- Automatic publishing to GitHub Releases with release notes and SHA-256 digests

---

## 📜 License & Compliance

Distribution packages are licensed for personal and community use. See [SECURITY.md](SECURITY.md) for vulnerability disclosure procedures.
