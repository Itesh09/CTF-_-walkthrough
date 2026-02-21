# 🏆 myVulnApp CTF Walkthrough

**Platform:** Intentionally Vulnerable CTF Training Platform  
**Target:** `http://152.42.242.139:5000`  
**Initial Credentials:** `bob` / `bob123`  
**Flags Captured:** 20/20  
**Date:** February 2026

## 📋 Overview

This repository contains a comprehensive walkthrough of the myVulnApp CTF challenge, demonstrating 20 common web vulnerabilities including SQL injection, IDOR, file upload bypass, path traversal, and more.

## 🚀 Quick Links

- [Complete Walkthrough](./walkthrough/)
- [All Flags](./flags/flags.txt)
- [Commands Used](./tools/commands.md)
- [Payloads](./tools/payloads.txt)

## 🎯 Vulnerabilities Discovered

| # | Vulnerability | Severity | Location |
|---|---------------|----------|----------|
| 1 | SQL Injection | Critical | Search |
| 2 | IDOR (Profile) | High | Profile |
| 3 | File Upload Bypass | Critical | Upload |
| 4 | XSS (Stored) | Medium | Upload/Notes |
| 5 | Path Traversal | High | File Download |
| 6 | Directory Enumeration | Medium | Web Root |
| 7 | Debug Backup Exposure | Medium | /debug |
| 8 | Plaintext Passwords | Critical | /password_viewer |
| 9 | Admin Panel Exposure | High | /admin |
| 10 | Database Exposure | Critical | app.db |
| 11 | Missing Security Headers | Low | HTTP Response |
| 12 | Insecure Cookies | Medium | Session |
| 13 | HTTP Header Injection | Medium | Various |
| 14 | Timing Attack | Low | Login |
| 15 | Debug API | Medium | /debug_api |
| 16 | CSRF Missing | Medium | Forms |
| 17 | Weak Session Token | High | Session |
| 18 | Session Fixation | Medium | Login |
| 19 | Logic Injection | Medium | Search |
| 20 | Authentication Bypass | Critical | Login |

## 📸 Screenshots

All screenshots are available in the [images](./images/) directory.

## 🛠️ Tools Used

- Web Browser (Firefox/Chrome)
- Burp Suite Community Edition
- Gobuster
- cURL
- SQLite3
- Python 3
- Flask-Unsign

## 📝 License

This walkthrough is for educational purposes only.

## 👤 Author

Itesh09
