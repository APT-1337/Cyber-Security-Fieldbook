# ✉️ Email Fundamentals

## 📋 Email Headers
Email headers are metadata lines attached to an email. They contain technical details such as sender, recipient, subject, routing information, and timestamps — crucial for forensic analysts and investigators.

---

## 📝 Email Body
The body is the main content of the email. It can include:
- Plain or formatted text
- Images
- Links
- Attachments (PDFs, DOCs, etc.)

---

## 📧 Email Addresses Structure
Example: `bob.smith@example.com`
- **bob.smith** → Local part (mailbox).
- **example.com** → Domain part.
- **.com** → Top-Level Domain (TLD).

---

## 📨 Email Protocols

### 🔹 SMTP – Simple Mail Transfer Protocol
- Used to **send outgoing mail**.
- Works on port:
  - 25 (plain)
  - 465 (SMTPS – SSL)
  - 587 (SMTPS – TLS)

---

### 🔸 POP3 – Post Office Protocol v3
- Downloads emails to local device and **deletes them from the server**.
- Not suitable for syncing across multiple devices.
- Ports:
  - 110 (plain)
  - 995 (POP3S – SSL/TLS)

---

### 🔸 IMAP – Internet Message Access Protocol
- Advanced protocol that **synchronizes** email across multiple devices.
- Keeps emails on the server.
- Ports:
  - 143 (plain)
  - 993 (IMAPS – SSL/TLS)

---

## 📦 Mail Agents

### 🔁 Mail Transfer Agent (MTA)
- Routes and transfers emails between mail servers.
- Example: Postfix, Exim.

### 📨 Mail User Agent (MUA)
- Software that users interact with to send/receive/manage emails.
- Examples: Gmail, Outlook, Thunderbird.

### 📬 Mail Delivery Agent (MDA)
- Accepts incoming messages from MTA.
- Delivers them to the user's inbox (mailbox).

### 📤 Mail Submission Agent (MSA)
- Submits the email to the mail system for delivery.
- Often acts as a gatekeeper for outgoing mail.

### 📥 Mail Retrieval Agent (MRA)
- Pulls messages from a remote mail server and delivers them to a local system.

> 📝 **Note:** We focus on **MTA, MUA, MDA** because **MSA and MRA** are **not officially supported by IETF** as standalone standards.
