# 06 - Directory Enumeration

## Objective
Discover hidden directories and files.

## Tools

- gobuster
- dirb
- ffuf

## Commands

```bash
gobuster dir -u http://target.com -w /usr/share/wordlists/dirb/common.txt
```

## Common Locations to Check

- `/admin/`
- `/backup/`
- `/debug/`
- `/logs/`
- `/api/`
- `/.git/`
- `/.env`

## Flag

Find a hidden directory containing sensitive information.
