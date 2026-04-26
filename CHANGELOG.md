# Changelog

All notable changes to this project will be documented in this file.

---

## [1.3.0] — 2025

### Added
- Initial release
- Auto-detection of IOC type: IP, domain, MD5/SHA1/SHA256 hash, URL
- AbuseIPDB integration — abuse confidence score, total reports, ISP, country
- VirusTotal integration — engine detections for all IOC types
- IPInfo integration — geolocation, ASN, org for IPs
- URLScan.io integration — scan submission for URLs and domains
- Composite 0–100 threat score engine
- MITRE ATT&CK technique mapping by IOC type and score
- Live enrichment log with timestamps
- JSON report export
- API keys stored in localStorage (browser-only)
- Zero-install single HTML file deployment
- Animated score counter and progress bar
- Example IOC chips for quick testing
- Responsive layout for desktop and mobile
