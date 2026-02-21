# 07 - Debug Backup

## Objective
Find and analyze debug/backups files exposed on the server.

## Common Backup Extensions

- `.bak`
- `.old`
- `.tmp`
- `.swp`
- `.zip`
- `.tar.gz`
- `.sql`

## Locations to Check

- Root directory
- Hidden directories found earlier
- Source code directories

## Analysis

1. Download the backup file
2. Examine for sensitive information
3. Look for credentials, API keys, or flags

## Flag

Find the debug backup file and extract the flag.
