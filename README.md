# 🔐 OWASP Juice Shop – Vulnerability Assessment & Penetration Testing (VAPT)

Welcome to my Vulnerability Assessment & Penetration Testing (VAPT) project focused on **OWASP Juice Shop** — one of the most popular intentionally vulnerable web applications. This repository demonstrates how common web security vulnerabilities can be discovered and exploited in a controlled environment using ethical hacking practices.

---

## 📁 Project Structure

juice-shop-vapt/
├── Findings/
│ ├── injection/
│ │ ├── admin-login-sqli.md
│ │ ├── blind-sqli-delay.md
│ │ └── union-sqli.md
│ ├── xss/
│ │ ├── dom-xss.md
│ │ ├── reflected-xss.md
│ │ └── stored-xss.md
│ ├── broken-access-control/
│ │ ├── access-admin-section.md
│ │ ├── basket-access.md
│ │ └── review-edit.md
│ ├── idor/
│ │ ├── order-access.md
│ │ ├── invoice-download.md
│ │ └── order-modify.md
│ ├── sensitive-data-exposure/
│ │ ├── cat-photo.md
│ │ ├── backup-access.md
│ │ └── internal-docs.md
│ ├── security-misconfiguration/
│ │ ├── access-logs.md
│ │ ├── b2b-api.md
│ │ └── cors.md
│ └── auth-session/
│ ├── sql-bypass-login.md
│ ├── reset-token-abuse.md
│ └── persistent-session.md
├── Reports/
│ └── Screenshots/
│ ├── Injection/
│ ├── XSS/
│ │ ├── DOM/
│ │ ├── Reflected/
│ │ └── Stored/
│ ├── BrokenAccessControl/
│ ├── IDOR/
│ ├── SensitiveDataExposure/
│ ├── SecurityMisconfiguration/
│ └── AuthSession/
├── Tools_Used.md
└── README.md



---

## ✅ Vulnerabilities Covered (with Categories)

| # | Category                   | Sample Labs                                                              | Screenshot Folder                   |
|---|----------------------------|---------------------------------------------------------------------------|--------------------------------------|
| 1 | **Injection**              | Admin Login via SQLi, Blind SQLi (Delay), Union SQLi                      | `Screenshots/Injection/`            |
| 2 | **Cross-Site Scripting**   | DOM XSS, Reflected XSS in Order Tracking, Stored XSS in Reviews          | `Screenshots/XSS/DOM`, `Reflected`, `Stored` |
| 3 | **Broken Access Control**  | Access Admin Section, View Other’s Basket, Modify/Delete Review          | `Screenshots/BrokenAccessControl/`  |
| 4 | **IDOR**                   | View Other’s Orders, Download Invoice, Modify Order via URL              | `Screenshots/IDOR/`                 |
| 5 | **Sensitive Data Exposure**| Retrieve Cat Photo, Backup File Access, Access Internal Docs             | `Screenshots/SensitiveDataExposure/`|
| 6 | **Security Misconfiguration** | Access Logs, Deprecated B2B API, Insecure CORS                         | `Screenshots/SecurityMisconfiguration/`|
| 7 | **Auth & Session Issues**  | SQL Login Bypass, Tokenless Password Reset, Persistent Session           | `Screenshots/AuthSession/`          |

> Each report contains payloads, Burp Suite steps, screenshots, vulnerability impact, and suggested mitigations.

---

## 📸 Screenshot Integration

Screenshots for each vulnerability are stored under:

- `Reports/Screenshots/<Category>/<Specific Attack>/`
- Use Markdown like this in your reports:

```markdown
![Proof-of-Concept](../Reports/Screenshots)



🚀 How to Use This Repository
1. Clone the repository:  git clone https://github.com/lucky-cyber3008/juice-shop-vapt.git

2. Read vulnerability write-ups under the Findings/ folder organized by category.

3. Explore screenshots under Reports/Screenshots/ for PoC images.

4. Use this as a reference for learning, bug bounty prep, or VAPT methodology.

🙋‍♂️ Author
Lucky
GitHub: @lucky-cyber3008
Cybersecurity Enthusiast | Bug Bounty Learner | Ethical Hacker in Training


📜 Disclaimer
This repository is intended for educational and ethical use only. All vulnerabilities demonstrated are part of OWASP Juice Shop — an intentionally vulnerable web application. Do not attempt these techniques on unauthorized systems. Always act responsibly and legally.
