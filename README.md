# 🔐 OWASP Juice Shop – Vulnerability Assessment & Penetration Testing (VAPT)

Welcome to my Vulnerability Assessment & Penetration Testing (VAPT) project focused on **OWASP Juice Shop** — one of the most popular intentionally vulnerable web applications. This repository demonstrates how common web security vulnerabilities can be discovered and exploited in a controlled environment using ethical hacking practices.

---

## 📁 Project Structure

- `juice-shop-vapt/`
  - `Findings/` – Vulnerability write-ups in Markdown
    - `dom-xss.md`
    - `idor.md`
    - `broken-access-control.md`
    - `sensitive-data-exposure.md`
    - `security-misconfiguration.md`
  - `Reports/`
    - `Screenshots/` – Proof-of-concept screenshots
      - `DOM/`
      - `IDOR/`
      - `BAC/`
      - `SDE/`
      - `Misconfig/`
  - `Tools_Used.md` – Tools used during the assessment
  - `README.md` – Project overview



---

## ✅ Vulnerabilities Covered

| #   | Vulnerability                  | Write-Up File                        | Screenshot Folder             |
|-----|-------------------------------|--------------------------------------|-------------------------------|
| 1   | DOM-Based XSS                 | `Findings/dom-xss.md`                | `Reports/Screenshots/DOM`     |
| 2   | Insecure Direct Object Ref.   | `Findings/idor.md`                   | `Reports/Screenshots/IDOR`    |
| 3   | Broken Access Control         | `Findings/broken-access-control.md`  | `Reports/Screenshots/BAC`     |
| 4   | Sensitive Data Exposure       | `Findings/sensitive-data-exposure.md`| `Reports/Screenshots/SDE`     |
| 5   | Security Misconfiguration     | `Findings/security-misconfiguration.md` | `Reports/Screenshots/Misconfig` |

> Each report contains payloads, Burp Suite steps, screenshots, vulnerability impact, and suggested mitigations.

---

## 📸 Screenshot Integration

Screenshots for each vulnerability can be found under their respective folders inside `Reports/Screenshots/`.  
In Markdown reports, they are embedded like:

```markdown
![Proof-of-Concept](../Reports/Screenshots/)

🚀 How to Use This Repository
1 Clone the repository: git clone https://github.com/lucky-cyber3008/juice-shop-vapt.git

2 Read vulnerability details in the Findings/ folder.

3 Explore screenshots under Reports/Screenshots/ for proof-of-concepts.

4 Use this as a reference for learning or preparing for ethical hacking, bug bounty, or OSCP-style assessments.


🙋‍♂️ Author
Lucky
GitHub: @lucky-cyber3008
Cybersecurity Enthusiast | Bug Bounty Learner | Ethical Hacker in Training

📜 Disclaimer
This repository is intended for educational and ethical purposes only. All vulnerabilities shown are exploited on OWASP Juice Shop — an intentionally vulnerable application. Do not attempt these techniques on unauthorized systems. Always follow responsible disclosure policies and the law.
OWASP Juice Shop, VAPT, Penetration Testing, Web Application Security, Bug Bounty, Ethical Hacking, DOM XSS, IDOR, Broken Access Control, Cybersecurity Portfolio, Juice Shop Report
