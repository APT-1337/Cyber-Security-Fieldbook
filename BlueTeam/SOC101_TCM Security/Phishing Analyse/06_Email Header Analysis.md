# 📧 Email Header Analysis – Methodology & Tools

This document provides a structured approach for analyzing email headers to detect phishing, spoofing, and other malicious activity. It includes explanation of key authentication mechanisms and essential tools.

---

## 🧭 Methodology Overview

### 🔍 1. Collect the Full Email Header
- Export or view full header from email client (e.g., Outlook, Gmail).
- Always analyze the **raw** header, not the visual rendering.

---

## 🧪 2. Analyze Key Header Fields

| Header Field      | Purpose                                                                 |
|-------------------|-------------------------------------------------------------------------|
| `Return-Path`     | Shows the address where bounces go; may differ from "From".            |
| `Received`        | Shows the hops from sender to recipient; trace original sending IP.     |
| `From`            | Claimed sender address (can be spoofed).                                |
| `Reply-To`        | Used in phishing to redirect replies to attacker-controlled address.    |
| `Message-ID`      | Unique ID of the message, often includes sending domain.                |
| `User-Agent`      | Email client used (may help detect bots or phish kits).                 |

---

## 🛡️ 3. Email Authentication Protocols

### ✅ SPF (Sender Policy Framework)
- Verifies if the sending IP is allowed to send emails for the domain.
- **Check:** `spf=pass` or `spf=fail` in header (usually in `Authentication-Results`).
- 🔧 Lookup:
```bash
nslookup -type=txt example.com | grep -i spf
dig TXT example.com +short | grep -i spf
```

### ✅ DKIM (DomainKeys Identified Mail)
- Uses a digital signature in the email header.
- Verifies the content wasn’t altered and was authorized by the domain owner.
- **Check:** `dkim=pass` or `dkim=fail`

### ✅ DMARC (Domain-based Message Authentication, Reporting & Conformance)
- Tells receiving mail servers what to do if SPF or DKIM fails.
- Policy examples:
  - `p=none`: monitor only
  - `p=quarantine`: mark as spam
  - `p=reject`: block the message
- **Check:** Look for `dmarc=pass/fail`

---

## 🧰 Recommended Tools

### 🔎 Header Analysis:
- [Microsoft Header Analyzer](https://mha.azurewebsites.net/)
- [MxToolbox Email Header Tool](https://mxtoolbox.com/Public/Tools/EmailHeaders)

### 🌐 WHOIS & Domain Info:
- [WHOIS Lookup](https://www.whois.com/whois/)
- [DomainTools WHOIS](https://whois.domaintools.com/)

---

## 🔄 Workflow Example

1. Paste email header into  MXToolbox for auto-parsing.
2. Manually inspect `Received` fields (last hop = attacker IP).
3. Perform WHOIS on sender domain and IP.
4. Check SPF, DKIM, DMARC alignment.
