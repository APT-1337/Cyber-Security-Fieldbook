# 🎣 Phishing Analysis Methodology

A structured approach to investigate and respond to phishing emails effectively.

---

## 1. 🚨 Initial Triage
- Quickly assess and prioritize the phishing email.
- Determine urgency and potential impact.

## 2. 📨 Header and Sender Examination
- Investigate Message Authentication Technologies (SPF, DKIM, DMARC).
- Analyze sender address, return-path, IPs, and other metadata.
- Identify the true origin and check the authenticity of the sender.

## 3. 📄 Content Examination
- Analyze the email body for tone, language, and formatting inconsistencies.
- Identify signs of social engineering or psychological manipulation.

## 4. 🌐 Web and URL Examination
- Collect all embedded URLs and related artifacts.
- Use tools (e.g., VirusTotal, urlscan.io) to inspect and analyze domains and redirects.

## 5. 📎 Attachment Examination
- Safely extract and analyze attachments in a sandboxed environment.
- Check file reputation and behavior.

## 6. 🔍 Contextual Examination
- Assess the broader context of the attack (recent trends, known campaigns).
- Look for patterns, targeted users, or larger-scale indicators.

## 7. 🛡️ Defense Measures
- Take **reactive actions** (e.g., block domains, isolate devices).
- Take **proactive actions** (e.g., update detection rules, improve awareness).
- Communicate with affected users and relevant stakeholders.

## 8. 📝 Documentation & Reporting
- Document all findings, verdicts, and actions taken in a clear report.
- Ensure all alerts and tickets are closed out properly.

---

