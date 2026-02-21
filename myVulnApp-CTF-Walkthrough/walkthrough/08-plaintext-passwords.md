# 08 - Plaintext Passwords

## Objective
Find exposed passwords in the application.

## Common Locations

- Source code comments
- Configuration files
- Log files
- Database
- JavaScript files

## Search Patterns

```bash
grep -r "password" .
grep -r "passwd" .
grep -ri "api.key" .
```

## Flag

Locate the plaintext password to get the flag.
