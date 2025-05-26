# 🔐 OWASP Juice Shop – Vulnerability Assessment & Penetration Testing (VAPT)

Welcome to my Vulnerability Assessment & Penetration Testing (VAPT) project focused on **OWASP Juice Shop** — one of the most popular intentionally vulnerable web applications. This repository demonstrates how common web security vulnerabilities can be discovered and exploited in a controlled environment using ethical hacking practices.

---

## 📁 Project Structure

```
juice-shop-vapt/
├── Findings/
│   ├── injection/
│   │   ├── admin-login-sqli.md
│   │   ├── no-sql-manipulation.md
│   │   └── union-sqli.md
│   ├── xss/
│   │   ├── dom-xss.md
│   │   ├── reflected-xss.md
│   │   └── bonus-paylaod.md
│   ├── broken-access-control/
│   │   ├── Forged-Feedback.md
│   │   ├── View-Another-User-Basket.md
│   │   └── review-edit.md
│   ├── improper-input-validation/
│   │   ├── Zero-star.md
│   │   ├── Empty-User-Registration.md
│   │   └── Admin-Registration.md
│   ├── sensitive-data-exposure/
│   │   ├── confidentail-document.md
│   │   ├── login-MCsafesearch.md
│   │   └── NFT-Takeover.md
│   ├── security-misconfiguration/
│       ├── Error-Handling.md
│       ├── Deprecated-Interface.md
      
├── Reports/
│   └── Screenshots/
│       ├── Injection/
│       ├── XSS/
│       │   ├── DOM/
│       │   ├── Reflected/
│       │   └── Bonus/
│       ├── BrokenAccessControl/
│       ├── IDOR/
│       ├── SensitiveDataExposure/
│       ├── SecurityMisconfiguration/
├── Tools_Used.md
└── README.md
```



---

## ✅ Vulnerabilities Covered (with Categories)

| # | Category                   | Sample Labs                                                              | Screenshot Folder                   |
|---|----------------------------|--------------------------------------------------------------------------|--------------------------------------|
| 1 | **Injection**              | Admin Login via SQLi, No-Sql-Manipulation, Union SQLi                    | `Screenshots/Injection/`            |
| 2 | **Cross-Site Scripting**   | DOM XSS, Reflected XSS in Order Tracking, Bonus Payload                  | `Screenshots/XSS/DOM`, `Reflected`, `Stored` |
| 3 | **Broken Access Control**  | Forged Feedback, View Other’s Basket, Modify/Delete Review               | `Screenshots/BrokenAccessControl/`  |
| 4 | **Improper-Input-Validation**| Zero-Star, Empty-User-Registration, Admin-Registration                   | `Screenshots/Improper-Input-Validation/`                 |
| 5 | **Sensitive Data Exposure**| Confidentail-Document, Login-MCsafesearch, NFT-TAkeover                  | `Screenshots/SensitiveDataExposure/`|
| 6 | **Security Misconfiguration** | Error-Handling, Deprecated-Interface, Insecure CORS                   | `Screenshots/SecurityMisconfiguration/`|


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


🚀 Want to dive into the code?  
👉 [Check out the GitHub Repository](https://github.com/lucky-cyber3008/juice-shop-vapt)

