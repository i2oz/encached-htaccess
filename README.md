# Encached .htaccess

![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)
![Compatibility](https://img.shields.io/badge/Server-Apache%202.2%20%7C%202.4%20%7C%20LiteSpeed-blue)
![PHP](https://img.shields.io/badge/PHP-7.4%20%7C%208.x-purple)

A performance- and security-focused Apache `.htaccess` configuration for PHP applications, optimized for AlmaLinux with cPanel/WHM on Apache 2.2/2.4 or LiteSpeed, and tested with PHP 7.4 & 8.x. Provides hardened rules for WordPress, Laravel, CodeIgniter, Joomla, XenForo, and more.

---

## 📦 Features

- **Security Hardening**
  - Disables directory listings, hides server signatures & sensitive headers
  - Modern HTTP security headers (CSP, HSTS, X-Frame-Options, Referrer-Policy, Permissions-Policy)
  - WAF-style filters blocking SQLi/LFI/XSS, malicious user-agents, referer spam, dangerous methods & long requests
  - Protects config files and core directories (WordPress, Joomla, Drupal, Magento, Laravel, CodeIgniter, XenForo, VCS folders)
  - IP-based allowlist for critical files

- **⚡ Performance Optimization**
  - Conditional caching & compression when LiteSpeed isn’t present
  - `mod_expires` for long-term cache on static assets
  - `mod_deflate`/`mod_brotli` compression
  - Avoids duplicate headers with LiteSpeed Cache plugin

- **🌐 Wide Compatibility**
  - Apache 2.2/2.4 or LiteSpeed Web Server
  - AlmaLinux / CentOS / RHEL with cPanel/WHM
  - PHP 7.4 & 8.x
  - Works alongside CMS rewrites (WordPress, Laravel, etc.)

---

## 🚀 Installation

1. **Backup** existing `.htaccess`:
   ```bash
   cp .htaccess .htaccess.backup
   ```
2. **Copy** this `.htaccess` into your site’s root.
3. **Merge** above existing CMS rules if present.
4. **Customize** IP placeholders:
   ```apache
   SetEnvIf REMOTE_ADDR "^YOUR_SERVER_IP_ESCAPED_1$" allow_ip
   SetEnvIf REMOTE_ADDR "^YOUR_ADMIN_IP_ESCAPED$" allow_ip
   ```
5. **(Optional)** Comment out `Strict-Transport-Security` if not using HTTPS.
6. **Test** in browser & DevTools; look for security headers and ensure no 403 on normal pages.

---

## 🤝 Contributing

1. Fork the repository  
2. Create a feature branch (`git checkout -b feature/your-change`)  
3. Commit your changes (`git commit -m 'Add new rule'`)  
4. Push to your branch (`git push origin feature/your-change`)  
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **Apache License 2.0**. See [LICENSE](LICENSE) for details.
