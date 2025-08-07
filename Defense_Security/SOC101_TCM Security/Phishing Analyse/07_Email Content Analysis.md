Email Content Analysis

A practical  guide for analyzing email **content** as part of phishing investigation or SOC operations. This complements header analysis by diving deeper into the **body, attachments, links, and behavior** of the email.

---

## 🎯 Objective

To examine the actual content of an email to identify malicious indicators, suspicious behaviors, and phishing attempts.

---

## 🧩 Key Analysis Areas

### 1. 📄 Email Body
- Look for suspicious **phrasing**, **urgency**, or **manipulative language**.
- Common red flags:
  - “Your account will be closed”
  - “Click here immediately”
  - Spoofed sender names or fake branding.

### 2. 🔗 Links (URLs)
- **Hover over links** to compare displayed vs actual URLs.
- Use the following tools to safely analyze:
  - 🔍 [urlscan.io](https://urlscan.io) – Full behavioral scan of URLs.
  - 🔧 [CyberChef](https://gchq.github.io/CyberChef/) – Decode obfuscated URLs (Base64, HEX, ROT13).
  - 🔎 [VirusTotal](https://virustotal.com) – Scan URLs and files for known malware.

### 3. 📎 Attachments
- Check for:
  - Macros in Office documents.
  - Embedded scripts.
  - Uncommon file extensions (e.g., `.iso`, `.js`, `.lnk`).

### 4. 🧬 Obfuscation & Encoding
- Look for:
  - Base64/Hex encoded strings.
  - URL-encoding (`%41%42%43`).
  - JavaScript obfuscation.
- Tools:
  - 🧠 CyberChef
  - `strings`, `base64`, `xxd` (Linux CLI)

### 5. 📬 Reply-To & From Fields
- Always verify if the **"Reply-To"** address differs from the "From".
- Common in **Business Email Compromise (BEC)** attacks.


---

## 🧰 Recommended Tools Recap

| Tool                                           | Purpose                 |
| ---------------------------------------------- | ----------------------- |
| [CyberChef](https://gchq.github.io/CyberChef/) | Deobfuscation, decoding |
| [urlscan.io](https://urlscan.io)               | URL analysis            |
| [VirusTotal](https://virustotal.com)           | URL & file scanning     |

---

## ✅ Best Practices
- Always isolate and inspect suspicious content in **controlled environments**.
- Never open suspicious attachments on a production machine.
- Use **sandboxing** and **network isolation** for detonation.
- Correlate findings with **header analysis** and **SIEM logs**.
