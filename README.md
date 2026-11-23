# 🔐 Networkwalks Cybersecurity Program — Week 3: Password Cracking

![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Tasks](https://img.shields.io/badge/Tasks-3%2F3%20Complete-brightgreen)
![Program](https://img.shields.io/badge/Networkwalks-Cybersecurity%20Training-red)

**Student:** Simranjit Kaur (Simran)
**Program:** Networkwalks Cybersecurity Training — Week 3
**Focus Area:** Password Cracking & Hash Analysis

---

## 📖 Background

Password cracking is the process of recovering a password from a protected file or stored data. Security professionals use it to test how strong a password really is, and to demonstrate why weak or common passwords are a serious risk.

When a file (PDF, ZIP, Office document, etc.) is locked with a password, that password isn't stored in plain text — it's stored as a **hash**, a scrambled, one-way representation of it. To recover the original password, a cracking tool first **extracts the hash** from the file, then runs a **dictionary or brute-force attack** against it — trying candidate passwords until one produces a matching hash.

This week covers that exact workflow through three different approaches:

| Approach | Style |
|---|---|
| 🖥️ Command-line / GUI tool | John the Ripper + Johnny |
| 🌐 Browser-based tool | Networkwalks Hash Calculator + Password Cracker |
| 🤖 AI-assisted workflow | Hexstrike-AI MCP + Claude Desktop |

---

## ✅ Tasks Overview

| # | Task | Tools Used | Status |
|---|------|------------|--------|
| 1 | **[JTR + Johnny](./task1-jtr-johnny)** — cracked 3 locked PDFs | John the Ripper, Johnny GUI | ✅ Complete |
| 2 | **[Networkwalks Web Tools](./task2-networkwalks-tools)** — cracked 1 locked PDF | Hash Calculator, Password Cracker | ✅ Complete |
| 3 | **[AI-Assisted Cracking](./task3-ai-hexstrike-mcp)** — cracked 1 locked PDF via natural-language prompts | Hexstrike-AI MCP, JTR, Claude Desktop (Kali) | ✅ Complete |

---

## 🚩 Flags & Passwords Captured

| Task | PDF | Password Found | Flag |
|---|---|---|---|
| 1 | My Locked PDF1.pdf | `good-luck` | `nw{cybersecurity_flag_captured_2608}` |
| 1 | My Locked PDF2.pdf | `password1` | `nw{networkwalks_persistence_jtr_270521}` |
| 1 | My Locked PDF3.pdf | `1qaz2wsx` | `nw{networkwalks_flag_260821_1}` |
| 2 | My Locked PDF1 (WK3-PM2).pdf | `password1` | `nw{networkwalks_flag1_jtr_270521_1}` |
| 3 | My Locked PDF1.pdf (via AI/MCP) | `good-luck` | — |

---

## 📂 Repository Structure

```text
networkwalks-week3-password-cracking/
├── README.md                      ← you are here
├── task1-jtr-johnny/
│   ├── README.md                  ← step-by-step walkthrough with screenshots
│   └── 01.png ... 15.png
├── task2-networkwalks-tools/
│   ├── README.md                  ← step-by-step walkthrough with screenshots
│   └── 01.png ... 03.png
└── task3-ai-hexstrike-mcp/
    ├── README.md                  ← step-by-step walkthrough with screenshots
    └── 01.png ... 10.png
```

---

## 🛠️ Tech Stack

`John the Ripper` · `Johnny GUI` · `pdf2john / hashcat hash format` · `Networkwalks Hash Calculator` · `Networkwalks Password Cracker` · `Hexstrike-AI MCP` · `Claude Desktop` · `Kali Linux`

---

## 🔑 Key Takeaway

Encryption is reversible with the right key; **hashing is one-way**. Cracking tools don't "decrypt" a password — they extract its hash and guess-and-check against it. That's why a weak password like `password1` falls in under a second, while a long, random, unique password can resist this kind of attack for years. Task 3 also showed that the same workflow can be driven conversationally through an AI agent connected to real security tools via MCP — the underlying cryptography doesn't change, just the interface.

---

*Educational lab work completed as part of the Networkwalks Cybersecurity Training program. All target files were provided by the instructor for authorized practice only.*
