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

*A self-contained, single-file portfolio with a live admin panel, secret triggers, and persistent stats.*

[![HTML5](https://img.shields.io/badge/HTML5-Single%20File-E34F26?style=flat-square&logo=html5&logoColor=white)](.)
[![No Dependencies](https://img.shields.io/badge/Dependencies-Zero-00ff9d?style=flat-square)](#)
[![Offline Ready](https://img.shields.io/badge/Offline-Ready-00cfff?style=flat-square)](#)
[![Admin Protected](https://img.shields.io/badge/Admin-Secret%20Trigger-ff3c6e?style=flat-square)](#-secret-admin-access)

</div>

---

## Overview

This is the personal cybersecurity portfolio of **Jesvin Bruce J** (alias: `TraceHanami` / `ZeroKira`), a 2nd-year B.E. Computer Science & Engineering student specializing in Cyber Security at Sri Shakthi Institute of Engineering & Technology, Coimbatore.

Built as a **zero-dependency, single HTML file** — no frameworks, no build step, no server required. Just open it in a browser.

---

## Features

### Portfolio Sections

| Section | Description |
|---|---|
| **Terminal** | Hero dashboard with live stats, profile, team info, and a live ticker |
| **Academics** | CGPA ring chart, coursework timeline, certifications |
| **Skills** | Animated skill bars, cybersecurity domains, tools & OS |
| **CTF** | Full competition history with rankings, team info, focus areas |
| **Platforms** | PicoCTF, Hack The Box, TryHackMe, LeetCode progress |
| **Contact** | Links, contact form, goals & career objectives |

### Technical Highlights

- **Zero dependencies** — no npm, no bundler, no backend
- **Single `.html` file** — share, host, or open locally with one file
- **Offline-first** — works without internet; fonts fall back to system fonts instantly
- **Persistent stats** — all data saved to `localStorage`, survives browser restarts
- **Live ticker** — animated stats bar auto-populated from your data
- **Particle canvas** — animated network background with zero library overhead
- **Custom cursor** — smooth cursor + ring follow effect
- **Fully responsive** — works on mobile, tablet, and desktop

---

## Admin Panel — Live Updates

The portfolio includes a built-in **Admin Panel** that lets you update all stats without touching code. Changes save instantly to the browser and persist across sessions.

### What You Can Update

| Tab | Fields |
|---|---|
| **Flag Counts** | PicoCTF easy/medium flags, HTB rank, Starting Point progress, HTB flags, LeetCode solved count & acceptance rate, CGPA |
| **CTF Events** | Add new competitions (name, rank, org, type, team, date, notes) — or delete old ones |
| **Platforms** | Log new HTB machines completed |
| **Profile** | Year/status text, best result summary, live ticker goal message |

All edits propagate instantly across every section of the portfolio — dashboard hero, stats row, CTF history, platform cards, and the live ticker.

---

## Secret Admin Access

The Admin button is **completely invisible** to visitors. There is no visible button, no hint, and no way to find it by browsing.

### How to Open the Admin Panel

| Device | Secret Trigger |
|---|---|
| **Desktop / Laptop** | Type `t` → `h` → `Enter` anywhere on the page |
| **Mobile / Tablet** | **Triple-tap** the `JESVIN BRUCE J` name on the hero section |

### Security Behaviour

- The button appears only after the correct trigger
- It **auto-hides after 30 seconds** of inactivity
- It **hides again** when the admin panel is closed
- Requires a **passphrase** to actually open the panel (session-locked)
- Auto-locks when the browser tab is closed

### Changing the Passphrase

Open the HTML file in any text editor and find:

```javascript
const PASSPHRASE = 'tracehanami2025';
```

Replace `tracehanami2025` with any passphrase you choose.

### Changing the Secret Key Trigger

```javascript
const REVEAL_SEQ = ['t', 'h', 'Enter'];
```

Change the array to any key sequence you want, e.g. `['T', 'H', 'X', 'Enter']`.

> **Note:** This is client-side protection — the passphrase is readable in source code by someone who knows to look. For a portfolio file, this provides solid casual protection. For stronger security, host behind a real server-side auth layer.

---

## Getting Started

### Open Locally

```bash
# No installation needed — just open the file
open tracehanami-portfolio.html        # macOS
start tracehanami-portfolio.html       # Windows
xdg-open tracehanami-portfolio.html   # Linux
```

Or drag and drop the file into any browser window.

### Host Online

Upload the single `.html` file to any static host:

| Platform | Steps |
|---|---|
| **GitHub Pages** | Push to a repo → Settings → Pages → Deploy from branch |
| **Netlify Drop** | Go to [netlify.com/drop](https://app.netlify.com/drop) → drag the file |
| **Vercel** | `vercel --prod` in the folder containing the file |
| **Any web server** | Copy the file to your `/public` or `/www` directory |

> ⚠️ **Important:** `localStorage` data (your admin-saved stats) is tied to the domain. If you change hosting domains, you will need to re-enter your stats in the Admin Panel once.

---

## Customisation Guide

### Updating Stats (Recommended: Admin Panel)

Use the secret trigger + passphrase to open the Admin Panel and update everything visually.

### Updating Stats (Manual: Code Edit)

Open the file in a text editor and find the `DEFAULT_DATA` object:

```javascript
const DEFAULT_DATA = {
  pico_easy: 81,        // PicoCTF easy flags
  pico_med: 70,         // PicoCTF medium flags
  htb_rank: 928,        // Hack The Box global rank
  htb_sp: 39,           // Starting Point completed
  htb_flags: 2,         // HTB flags captured
  lc_solved: 9,         // LeetCode problems solved
  lc_acc: 63.64,        // LeetCode acceptance rate (%)
  cgpa: 8.54,           // Current CGPA
  ctf_events: [ ... ],  // Array of CTF competition objects
  htb_machines: [ ... ] // Array of HTB machines completed
};
```

Edit the values and save. These are the defaults — the Admin Panel overrides them via `localStorage`.

### Adding a Profile Photo

Place your photo in the same folder as the HTML file and update:

```html
<img src="meee.png" alt="Jesvin Bruce J" ... />
```

Replace `meee.png` with your image filename. Supported formats: JPG, PNG, WebP. If the image fails to load, a fallback ninja icon displays automatically.

### Changing Fonts

The portfolio uses three Google Fonts with system fallbacks:

```css
--font-mono: 'JetBrains Mono', 'Consolas', 'Courier New', monospace;
--font-body: 'Rajdhani', 'Segoe UI', system-ui, sans-serif;
--font-head: 'Orbitron', 'Segoe UI', system-ui, sans-serif;
```

Replace the first value in each variable with any Google Font name, then update the `<link>` preload URL at the top of the file accordingly.

### Changing the Colour Scheme

All colours are CSS variables at the top of the `<style>` block:

```css
:root {
  --acid:  #00ff9d;   /* Primary neon green */
  --acid2: #00cfff;   /* Secondary electric blue */
  --warn:  #ff3c6e;   /* Accent / alert red-pink */
  --gold:  #ffd24c;   /* Gold for top rankings */
  --bg:    #020a0f;   /* Main background */
}
```

---

## Project Structure

```
tracehanami-portfolio.html   ← The entire portfolio (single file)
meee.png                     ← Profile photo (optional, place alongside HTML)
jesvin-profile.vcf           ← vCard contact file (optional)
README.md                    ← This file
```

---

## CTF Profiles & Platforms

| Platform | Handle | Link |
|---|---|---|
| PicoCTF | TraceHanami | [play.picoctf.org](https://play.picoctf.org) |
| Hack The Box | TraceHanami | [hackthebox.com](https://www.hackthebox.com) |
| TryHackMe | TraceHanami | [tryhackme.com](https://tryhackme.com) |
| LeetCode | — | [leetcode.com](https://leetcode.com) |
| CTFtime | Moonlitcipher | [ctftime.org](https://ctftime.org) |

---

## Competition History Snapshot

| Rank | Event | Type | Team |
|---|---|---|---|
| 🥉 3rd | Flag Quest @ KALAM 2025 | National | Moonlitcipher |
| 12th | OxTi HackTiVate @ Titanium 2026 | National | TraceHanami, Sandy, Asta_Black |
| 14th | Enigma CTF 2026 @ IIT Hyderabad | National | Moonlitcipher |
| 23rd | L3m0n CTF 2025 | National | TraceHanami, Zer0logon, Adharsha, Devi K |
| 29th | Pentathon 2025 | Online | ZeroKira, Zerologon, J2006, Whitedevil, DEVI.K |
| 199th | BSidesSF 2025 CTF | International | ZeroKira, CyberGhost05, Santhosh, DEVI.K |
| — | Binary×Forge @ KRIYA 2025 *(First CTF)* | College | Moonlitcipher |
| — | EXPLOIT-X KPR CTF | International | Moonlitcipher |
| — | H7CTF 2025 | International | TraceHanami, Devi K |
| — | ISEA ISAP CTF 2026 | National (IIT Madras) | TraceHanami |

*Full history viewable in the CTF section of the portfolio.*

---

## Tech Stack

| Layer | Technology |
|---|---|
| Markup | HTML5 |
| Styling | CSS3 (custom properties, grid, animations) |
| Logic | Vanilla JavaScript (ES2020+) |
| Storage | `localStorage` (persistent) + `sessionStorage` (auth) |
| Fonts | Google Fonts (async, non-blocking) + system fallbacks |
| Icons | Font Awesome 6.5 (async) |
| Graphics | Canvas API (particle network) |

**No build tools. No frameworks. No node_modules.**

---

## Browser Support

| Browser | Support |
|---|---|
| Chrome / Edge (modern) | ✅ Full |
| Firefox (modern) | ✅ Full |
| Safari (modern) | ✅ Full |
| Mobile Chrome / Safari | ✅ Full |
| IE 11 | ❌ Not supported |

---

## Contact

**Jesvin Bruce J** — `TraceHanami` / `ZeroKira`

- **Email:** [clesturbruce@gmail.com](mailto:clesturbruce@gmail.com)
- **LinkedIn:** [linkedin.com/in/jesvin-bruce-j-a2154a319](https://www.linkedin.com/in/jesvin-bruce-j-a2154a319)
- **GitHub:** [github.com/TraceHanami](https://github.com/TraceHanami)
- **Team:** Moonlitcipher · Sakura Sentinels

---

<div align="center">

*"Building deep roots in cybersecurity through CTFs, persistence, and relentless learning."*

**2nd Year · CSE (Cyber Security) · Sri Shakthi Institute of Engineering & Technology**

</div>
