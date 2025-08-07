
# 🔍 URL Analysis Field Guide

Analyzing suspicious URLs is a fundamental task in phishing investigations and threat intelligence. This guide provides key steps and tools to analyze a URL effectively, identify malicious behavior, and extract indicators of compromise (IOCs).

---

## 🧠 Why Analyze URLs?

- Detect phishing campaigns
- Identify malware hosting domains
- Uncover shortened or obfuscated links
- Monitor blacklisted or suspicious domains

---

## 🛠️ Recommended Tools & Services

### 🧪 Reputation & Threat Intelligence

- **[PhishTank](https://phishtank.org)**  
  Crowdsourced phishing site database. Submit or search suspicious URLs.

- **[VirusTotal](https://www.virustotal.com/)**  
  Multi-engine scanner. Submit URLs to check for detection by AV engines and sandbox behaviors.

- **[URLVoid](https://www.urlvoid.com/)**  
  Domain reputation checker using multiple blacklists.

- **[URLhaus](https://urlhaus.abuse.ch/)**  
  Database of malware URLs maintained by abuse.ch, often linked with botnets and exploit kits.

- **[Google Safe Browsing Site Status](https://transparencyreport.google.com/safe-browsing/search)**  
  Check if Google has flagged the site as unsafe.

---

### 🔓 Link Unshortening

- **[Unshorten.it](https://unshorten.it/)**  
  Reveal the final destination of shortened URLs (bit.ly, t.co, etc.).

---

### 📸 Visual & Passive Analysis

- **[URL to PNG](https://www.url2png.com/)**  
  Render a visual snapshot of the website to analyze suspicious content without visiting it directly.

- **[WannaBrowser](https://www.wannabrowser.com/)**  
  Opens a URL in a remote, isolated browser environment to view content safely.

---

## 🧰 Advanced Inspection

- **[CyberChef](https://gchq.github.io/CyberChef/)**  
  Decode obfuscated URLs, base64, hex, or JavaScript-encoded redirects.

- Use `curl`, `wget`, or a proxy tool (e.g., Burp Suite) to inspect HTTP headers, redirection chains, and more.

---

## 🧵 URL Analysis Workflow

1. **Passive Inspection**
   - Unshorten if necessary
   - Screenshot with URL2PNG or WannaBrowser
   - Check domain reputation (PhishTank, VirusTotal, URLVoid)

2. **Structure Analysis**
   - Check for suspicious parameters (`?login=`, `password=`, etc.)
   - Look for encoded payloads or JavaScript

3. **Decode & Deobfuscate**
   - Use CyberChef to decode parts of the URL (base64, hex, ROT13, etc.)

4. **Threat Hunting**
   - Search URL or domain on URLhaus or VirusTotal for related IOCs
   - Reverse lookup IP addresses or WHOIS domain info

5. **Log the Result**
   - Note down indicators like final redirection domain, hosting country, ASN, etc.

---

## 🧠 Pro Tips

- Never click suspicious URLs directly — always use isolated analysis tools.
- Combine passive and active inspection to get a full picture.
- Pay attention to subtle typos in domains (e.g., g00gle.com).
- Note any SSL certificate anomalies (e.g., self-signed, expired).

---
