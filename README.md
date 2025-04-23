# 🛡️ OWASP-Based Website Security Testing Checklist

A comprehensive checklist for manual website security testing based on OWASP standards. Designed for both **beginners** and **professionals**.

---

## ✅ Table of Contents

- [Information Gathering](#information-gathering)
- [Configuration Management](#configuration-management)
- [Secure Transmission](#secure-transmission)
- [Authentication](#authentication)
- [Session Management](#session-management)
- [Authorization](#authorization)
- [Data Validation](#data-validation)
- [Denial of Service](#denial-of-service)
- [Business Logic](#business-logic)
- [Cryptography](#cryptography)
- [Risky Functionality - File Uploads](#risky-functionality---file-uploads)
- [Risky Functionality - Card Payment](#risky-functionality---card-payment)
- [HTML5](#html5)

---

## 🕵️ Information Gathering

- [ ] Manually explore the site (click around)
- [ ] Spider/crawl for hidden content (use tools like OWASP ZAP/Burp)
- [ ] Check `robots.txt`, `sitemap.xml`, `.DS_Store` (expose paths)
- [ ] Search engine cached pages (site:example.com)
- [ ] User-Agent based content differences (mobile vs desktop)
- [ ] Fingerprint app (Wappalyzer, BuiltWith)
- [ ] Identify technologies (JS, PHP, etc.)
- [ ] Identify user roles (admin, guest, user)
- [ ] Find entry points (login, upload, APIs)
- [ ] Review client-side code (view-source, dev tools)
- [ ] Look for multiple channels (web/mobile)
- [ ] Identify co-hosted apps (subdomains, IP neighbors)
- [ ] List all hostnames/ports (Nmap, dig, nslookup)
- [ ] Identify 3rd-party hosted content (CDNs, scripts)

---

## ⚙️ Configuration Management

- [ ] Common admin URLs (e.g. /admin, /dashboard)
- [ ] Backup/unreferenced files (e.g. .bak, .old)
- [ ] HTTP methods & Cross Site Tracing (OPTIONS/XST)
- [ ] File extension handling (upload .php.jpg etc.)
- [ ] Check for secure HTTP headers (CSP, HSTS, etc.)
- [ ] Policy files: Flash, Silverlight, robots.txt
- [ ] Staging/test data in production (e.g. test@example.com)
- [ ] Secrets in client code (JS files with API keys)

---

## 🔐 Secure Transmission

- [ ] SSL/TLS version, key length (test with SSL Labs)
- [ ] Valid digital cert (CA signed, CN match)
- [ ] Credentials only over HTTPS (no HTTP logins)
- [ ] Login form delivered via HTTPS (avoid mixed content)
- [ ] Session tokens only over HTTPS (secure flag)
- [ ] HTTP Strict Transport Security (HSTS enabled)

---

## 👤 Authentication

- [ ] User enumeration (check error messages)
- [ ] Authentication bypass (try skipping auth)
- [ ] Bruteforce protection (rate limit, CAPTCHA)
- [ ] Password complexity rules (e.g. 8+ chars, symbols)
- [ ] Remember me feature (token theft)
- [ ] Autocomplete disabled on login forms
- [ ] Password reset process (email/SMS validation)
- [ ] Change password flow (ask old password)
- [ ] CAPTCHA working (for bots)
- [ ] 2FA/MFA enabled (OTP, App)
- [ ] Logout functionality (and session expiry)
- [ ] No cached login pages (Pragma, Cache-Control headers)
- [ ] No default creds (admin/admin, etc.)
- [ ] Login history visible (optional but good)
- [ ] Notifications for password changes/lockouts
- [ ] Shared auth schemes consistent (SSO)
  
---

## 🕓 Session Management

- [ ] Understand session method (cookie/token/URL)
- [ ] Check `HttpOnly` & `Secure` flags
- [ ] Scope: path/domain restriction
- [ ] Cookie expiration (short-living)
- [ ] Auto logout after inactivity
- [ ] Terminate session on logout
- [ ] Check multiple sessions allowed
- [ ] Random session IDs (entropy)
- [ ] New session on login/logout
- [ ] Shared sessions consistent (SSO apps)
- [ ] Session puzzling attempts (re-use tokens)
- [ ] Test CSRF and Clickjacking protections

---

## 🔑 Authorization

- [ ] Path traversal (../etc/passwd)
- [ ] Authorization bypass (no token checks)
- [ ] Vertical privilege escalation (user → admin)
- [ ] Horizontal access issues (user1 → user2 data)
- [ ] Missing authorization checks

---

## 🛡️ Data Validation

- [ ] Reflected XSS (in URL, input)
- [ ] Stored XSS (saved in DB)
- [ ] DOM-based XSS (JS context)
- [ ] Cross Site Flashing (legacy)
- [ ] HTML Injection (break layout)
- [ ] SQL Injection (e.g. `' OR 1=1--`)
- [ ] LDAP/ORM/XXE/XML/XPath Injection
- [ ] SSI & Code Injection (eval, exec)
- [ ] Command Injection (`, ; &&`)
- [ ] Overflow & format string bugs
- [ ] HTTP splitting/smuggling
- [ ] Open redirect (redirect param)
- [ ] LFI/RFI (include other files)
- [ ] Compare client vs server validation
- [ ] NoSQL injection (MongoDB, etc.)
- [ ] HTTP parameter pollution (a[]=1&a[]=2)
- [ ] Mass assignment (POST unknown params)
- [ ] NULL/invalid session cookies

---

## 💣 Denial of Service (DoS)

- [ ] Anti-automation protections (rate limits)
- [ ] Account lockout mechanism (abuse protection)
- [ ] Protocol DoS (e.g. long headers)
- [ ] SQL wildcard DoS (LIKE '%%%')

---

## 🧠 Business Logic

- [ ] Feature abuse (e.g. referral rewards)
- [ ] Non-repudiation issues (no audit logs)
- [ ] Trust boundaries (user vs system)
- [ ] Data integrity checks
- [ ] Duty segregation (no 1 user does all)

---

## 🔐 Cryptography

- [ ] Sensitive data not encrypted (e.g. plain text passwords)
- [ ] Use of wrong/weak algorithms (e.g. MD5, SHA1)
- [ ] Missing salt in hashing
- [ ] Predictable randomness (e.g. `rand()`)

---

## 📁 Risky Functionality - File Uploads

- [ ] Whitelist file types only (e.g. .jpg, .pdf)
- [ ] Enforce file size limits
- [ ] File content matches type (magic bytes)
- [ ] AV scanning of uploads
- [ ] Filenames sanitized (no ../ etc.)
- [ ] Files stored outside webroot
- [ ] Different port/host for files
- [ ] File access controlled (auth)

---

## 💳 Risky Functionality - Card Payment

- [ ] Web server/app vuln scan (SSL, XSS, etc.)
- [ ] Guessable/default credentials
- [ ] Test/prod data separation
- [ ] Injection/Buffer overflow tests
- [ ] Secure crypto storage
- [ ] Transport layer security (TLS)
- [ ] Error handling (no leaks)
- [ ] CVSS > 4.0 vulnerabilities
- [ ] Auth/AuthZ issues
- [ ] CSRF protections

---

## 🌐 HTML5

- [ ] Test Web Messaging (`postMessage`)
- [ ] Web Storage SQLi (local/sessionStorage abuse)
- [ ] Check CORS implementation
- [ ] Offline Web App cache validation

---

## 💾 License

MIT License

---

## 🙌 Contributing

Pull requests welcome. For major changes, open an issue first.

