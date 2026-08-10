<div align="center">

```
████████╗██████╗  █████╗  ██████╗███████╗██╗  ██╗ █████╗ ███╗   ██╗ █████╗ ███╗   ███╗██╗
╚══██╔══╝██╔══██╗██╔══██╗██╔════╝██╔════╝██║  ██║██╔══██╗████╗  ██║██╔══██╗████╗ ████║██║
   ██║   ██████╔╝███████║██║     █████╗  ███████║███████║██╔██╗ ██║███████║██╔████╔██║██║
   ██║   ██╔══██╗██╔══██║██║     ██╔══╝  ██╔══██║██╔══██║██║╚██╗██║██╔══██║██║╚██╔╝██║██║
   ██║   ██║  ██║██║  ██║╚██████╗███████╗██║  ██║██║  ██║██║ ╚████║██║  ██║██║ ╚═╝ ██║██║
   ╚═╝   ╚═╝  ╚═╝╚═╝  ╚═╝ ╚═════╝╚══════╝╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═══╝╚═╝  ╚═╝╚═╝     ╚═╝╚═╝
```

**`TraceHanami // ZeroKira`** — Cybersecurity Portfolio

*A self-contained, high-performance portfolio featuring Web Crypto SHA-256 admin auth, DOM XSS protection, live stats, secret triggers, and zero dependencies.*

[![License: MIT](https://img.shields.io/badge/License-MIT-00ff9d.svg?style=flat-square)](LICENSE)
[![Security Audited](https://img.shields.io/badge/Security-Audited-00cfff?style=flat-square)](SECURITY.md)
[![Subresource Integrity](https://img.shields.io/badge/SRI-Enabled-ffd24c?style=flat-square)](#security--hardening)
[![Admin SHA-256 Protected](https://img.shields.io/badge/Admin-SHA--256-ff3c6e?style=flat-square)](#secret-admin-access)
[![GitHub Pages Deployment](https://img.shields.io/badge/GitHub%20Pages-Automated-00ff9d?style=flat-square&logo=github)](.github/workflows/deploy.yml)

</div>

---

## 🛡️ Security & Hardening Highlights

As a cybersecurity portfolio, this codebase is hardened against standard web vulnerabilities:

1. **SHA-256 Web Crypto Authentication**:
   - The Admin passphrase is validated using native `crypto.subtle.digest('SHA-256')`.
   - **Zero Plaintext Secrets**: Plaintext passwords are never hardcoded or committed to version control.
2. **DOM Cross-Site Scripting (XSS) Prevention**:
   - Strict HTML entity encoding (`escapeHTML()`) sanitizes all dynamic user inputs before DOM rendering.
3. **Subresource Integrity (SRI)**:
   - External stylesheets (FontAwesome) enforce cryptographic `sha512` integrity validation and `crossorigin="anonymous"`.
4. **Security Meta Headers**:
   - Includes `<meta http-equiv="Content-Security-Policy">`, `X-Content-Type-Options: nosniff`, `Referrer-Policy`, and `Permissions-Policy`.
5. **Zero Tracking & Zero Third-Party Dependencies**:
   - Pure HTML5/CSS3/Vanilla JS execution. No external tracking scripts, telemetry, or server-side vulnerabilities.

---

## 📌 Overview

This is the personal cybersecurity portfolio of **Jesvin Bruce J** (alias: `TraceHanami` / `ZeroKira`), a B.E. Computer Science & Engineering student specializing in Cyber Security at Sri Shakthi Institute of Engineering & Technology, Coimbatore.

---

## ⚡ Features

### Portfolio Sections

| Section | Description |
|---|---|
| **Terminal** | Hero dashboard with live stats, profile details, team affiliations, and live ticker |
| **Academics** | CGPA ring chart, coursework timeline, certifications |
| **Skills** | Animated skill bars, cybersecurity domains, tools & OS proficiencies |
| **CTF** | Full competition history with rankings, team info, and focus areas |
| **Platforms** | PicoCTF, Hack The Box, TryHackMe, and LeetCode progress |
| **Contact** | Contact links, vCard download, interactive form, and goals |

---

## 🔐 Secret Admin Access

The Admin Panel lets you visually update CTF flags, platform ranks, LeetCode stats, and goals.

### How to Unlock the Admin Panel

| Platform | Secret Trigger |
|---|---|
| **Desktop** | Type `t` → `h` → `Enter` anywhere on the page |
| **Mobile** | **Triple-tap** the `JESVIN BRUCE J` hero text |

### Changing Your Admin Passphrase

1. Generate a SHA-256 hash of your desired passphrase using Node.js:
   ```bash
   npm run hash-passphrase "myNewSecretPassphrase"
   ```
   *or via bash*:
   ```bash
   echo -n "myNewSecretPassphrase" | sha256sum
   ```
2. Open `index.html` and update `PASSPHRASE_HASH`:
   ```javascript
   const PASSPHRASE_HASH = 'your_generated_sha256_hash_here';
   ```

---

## 🚀 Getting Started

### Local Development / Preview

No complex build step is required. Run locally using npm:

```bash
# Clone the repository
git clone https://github.com/TraceHanami/portfolio.git
cd portfolio

# Start local dev server
npm start
```

Or simply open `index.html` in any modern web browser.

---

## 📄 License & Security Policy

- **License**: Released under the [MIT License](LICENSE).
- **Security Policy**: See [SECURITY.md](SECURITY.md) for vulnerability disclosure details.
