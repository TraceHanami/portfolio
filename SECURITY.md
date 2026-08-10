# Security Policy

## Reporting a Vulnerability

As a Cybersecurity Student & CTF Competitor portfolio repository, security is taken seriously. If you discover a security vulnerability within this project, please follow responsible disclosure practices.

### Preferred Contact

- **Email**: [clesturbruce@gmail.com](mailto:clesturbruce@gmail.com)
- **GitHub Security Advisory**: Open a private draft security advisory on this repository.

Please include:
1. Description of the issue / vulnerability.
2. Steps to reproduce or proof-of-concept (PoC).
3. Potential impact.

---

## Security Practices & Architecture

This repository adheres to the following security controls:

### 1. No Plaintext Credentials
- Admin access uses **Client-Side SHA-256 Hashing** via Web Crypto API (`crypto.subtle.digest`).
- Plaintext passphrases are **never** hardcoded or committed to version control.

### 2. DOM XSS Protection
- All dynamic data rendered into the DOM passes through HTML entity encoding (`escapeHTML()`).
- Unsanitized string interpolation into `innerHTML` is strictly prohibited.

### 3. Subresource Integrity (SRI) & Content Security Policy (CSP)
- External CDN assets (FontAwesome) use explicit **Subresource Integrity (SRI)** hashes (`sha512-...`) and `crossorigin="anonymous"`.
- Meta headers enforce strict Content Security Policy (CSP), `X-Content-Type-Options: nosniff`, and `Referrer-Policy: strict-origin-when-cross-origin`.

### 4. Zero Backend & Zero Third-Party Trackers
- Static HTML5/CSS3/Vanilla JS execution.
- No analytics trackers, no backend server vector, and no third-party cookie storage.

---

## Security Audit Status

- **Automated Scans**: CodeQL / Dependabot enabled
- **Secrets Audit**: Clean (0 plain text secrets in source or commit history)
- **XSS Audit**: Fully sanitized
