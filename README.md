# 🔍 Unified IOC Enrichment Tool

> A zero-install, browser-based threat intelligence tool for SOC analysts.  
> Paste any IP, domain, file hash, or URL — get a full enrichment report in seconds.

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Zero Install](https://img.shields.io/badge/install-zero-brightgreen)
![APIs](https://img.shields.io/badge/APIs-5-purple)

---

## 🚀 What Is This?

In a real SOC, when an alert fires, an analyst manually checks 5–6 different tools — AbuseIPDB, VirusTotal, Shodan, IPInfo, URLScan — one by one. That wastes 10–20 minutes per alert.

This tool solves that:

```
Paste IOC → auto-detects type → queries all APIs in parallel → unified threat report
```

**One tool. One paste. 30 seconds.**

---

## ✨ Features

| Feature | Details |
|---|---|
| **Auto-detection** | Automatically identifies IP, domain, MD5/SHA1/SHA256 hash, or URL |
| **4 API integrations** | AbuseIPDB · VirusTotal · IPInfo · URLScan.io |
| **Parallel queries** | All APIs queried simultaneously — no waiting |
| **Threat Score** | 0–100 composite score with animated display |
| **MITRE ATT&CK mapping** | Suggests relevant techniques based on IOC type and score |
| **JSON export** | Download full report as `.json` for SIEM/ticketing |
| **Zero install** | Pure HTML + CSS + JS — open the file and use it |
| **Runs anywhere** | Browser, USB stick, air-gapped machine — no Node, no Python, no server |
| **Key storage** | API keys saved locally in `localStorage` — never sent anywhere except the API itself |

---

## 🛠️ Supported IOC Types

| Type | Example | APIs Used |
|---|---|---|
| **IPv4 Address** | `45.33.32.156` | AbuseIPDB, VirusTotal, IPInfo |
| **Domain** | `malware-c2.xyz` | VirusTotal, URLScan.io |
| **File Hash** (MD5/SHA1/SHA256) | `d41d8cd98f00b204e9800998ecf8427e` | VirusTotal |
| **URL** | `http://evil.ru/payload.exe` | VirusTotal, URLScan.io |

---

## ⚡ Quick Start

### Option 1 — Direct file (recommended)
```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/ioc-enrichment-tool.git

# Open in browser — that's it
open ioc-enrichment-tool/index.html
```

### Option 2 — Download ZIP
1. Click **Code → Download ZIP** on GitHub
2. Extract the ZIP
3. Open `index.html` in any browser

### Option 3 — GitHub Pages
Deploy to GitHub Pages for instant web access:
1. Fork this repo
2. Go to **Settings → Pages → Source: main branch → / (root)**
3. Access at `https://YOUR_USERNAME.github.io/ioc-enrichment-tool/`

---

## 🔑 API Keys Setup

The tool works with any combination of keys — more keys = richer reports. All free tiers are sufficient for daily SOC use.

| API | Free Tier | Get Key |
|---|---|---|
| **AbuseIPDB** | 1,000 checks/day | [abuseipdb.com/account/api](https://www.abuseipdb.com/account/api) |
| **VirusTotal** | 4 lookups/min, 500/day | [virustotal.com/gui/user/apikey](https://www.virustotal.com/gui/user/apikey) |
| **IPInfo** | 50,000 req/month | [ipinfo.io/account/token](https://ipinfo.io/account/token) |
| **URLScan.io** | Free tier available | [urlscan.io/user/profile](https://urlscan.io/user/profile/) |

**Security note:** Keys are stored in your browser's `localStorage` only. They are sent directly to each API endpoint and nowhere else. The tool has no backend.

---

## 📸 Screenshot

> _Tool running in browser showing IP enrichment report with threat score, AbuseIPDB data, VirusTotal detections, geolocation, and MITRE ATT&CK techniques._

---

## 🧩 Project Structure

```
ioc-enrichment-tool/
├── index.html          ← The entire tool (single file)
├── README.md           ← This file
├── LICENSE             ← MIT License
└── CHANGELOG.md        ← Version history
```

The entire tool is **one self-contained HTML file** — no dependencies, no package.json, no build step.

---

## 🗺️ Roadmap

- [ ] **Bulk IOC mode** — paste a list of IOCs, enrich all at once
- [ ] **SIEM export** — export in Splunk/Wazuh-compatible JSON format
- [ ] **Historical lookups** — store past scans in localStorage
- [ ] **GreyNoise integration** — distinguish mass-scanners from targeted attackers
- [ ] **MalwareBazaar** — hash lookups with sample download links
- [ ] **Threat Feed import** — paste IOC lists from MISP or ThreatFox
- [ ] **PDF report** — one-click PDF export for ticket attachments
- [ ] **Dark/Light mode toggle**

---

## 🔧 How It Works

```
┌─────────────────────────────────────────────────┐
│              User pastes IOC                     │
└──────────────────────┬──────────────────────────┘
                       │
              ┌────────▼────────┐
              │  Type Detector  │
              │ IP/Domain/Hash/ │
              │      URL        │
              └────────┬────────┘
                       │
         ┌─────────────▼──────────────┐
         │     Parallel API Calls     │
         │                            │
         │  AbuseIPDB   VirusTotal    │
         │  IPInfo      URLScan.io    │
         │                            │
         └─────────────┬──────────────┘
                       │
         ┌─────────────▼──────────────┐
         │     Threat Score Engine    │
         │  Composite 0–100 score     │
         │  MITRE ATT&CK mapping      │
         └─────────────┬──────────────┘
                       │
         ┌─────────────▼──────────────┐
         │      Unified Report        │
         │  Score + Verdict + Cards   │
         │  JSON Export               │
         └────────────────────────────┘
```

---

## 📄 License

MIT License — free to use, modify, and distribute.  
Built by **Harudhan Kapoor** · SOC Analyst

---

## 🤝 Contributing

Pull requests welcome. For major changes, open an issue first.

1. Fork the repo
2. Create your branch: `git checkout -b feature/bulk-ioc`
3. Commit: `git commit -m 'Add bulk IOC mode'`
4. Push: `git push origin feature/bulk-ioc`
5. Open a Pull Request

---

## ⭐ If this helped you

Star the repo and share it with your SOC team. Every star helps it reach more analysts who need it.
