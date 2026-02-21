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
##Exploitation
simply add /password_viewer in url

## Screenshot
 ![Plain-text](../images/Plain-text.png)
