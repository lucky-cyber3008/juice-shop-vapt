# 🔐 OWASP Juice Shop – Vulnerability Assessment & Penetration Testing (VAPT)

Welcome to my VAPT project on **OWASP Juice Shop**, a deliberately insecure web application used for practicing and understanding common web security flaws.  
This project includes detailed write-ups and proof-of-concept screenshots for multiple OWASP Top 10 vulnerabilities.

---

## 📁 Project Structure

juice-shop-vapt/
│
├── Findings/ # Vulnerability write-ups in Markdown
│ ├── dom-xss.md
│ ├── idor.md
│ ├── broken-access-control.md
│ ├── sensitive-data-exposure.md
│ └── security-misconfiguration.md
│
├── Reports/
│ └── Screenshots/ # Proof-of-concept screenshots
│ ├── DOM/
│ ├── IDOR/
│ ├── BAC/
│ ├── SDE/
│ └── Misconfig/
│
├── Tools_Used.md # Tools used during the assessment
└── README.md # Project overview


---

## ✅ Vulnerabilities Covered

| #   | Vulnerability                  | Write-Up File                    | Screenshots Folder        |
|-----|-------------------------------|----------------------------------|---------------------------|
| 1   | DOM-Based XSS                 | `Findings/dom-xss.md`            | `Reports/Screenshots/DOM` |
| 2   | Insecure Direct Object Ref.   | `Findings/idor.md`               | `Reports/Screenshots/IDOR`|
| 3   | Broken Access Control         | `Findings/broken-access-control.md` | `Reports/Screenshots/BAC`  |
| 4   | Sensitive Data Exposure       | `Findings/sensitive-data-exposure.md` | `Reports/Screenshots/SDE`  |
| 5   | Security Misconfiguration     | `Findings/security-misconfiguration.md` | `Reports/Screenshots/Misconfig` |

> Each write-up includes the payload used, reproduction steps, screenshots, impact, and mitigation.

---

## 📸 Example Screenshot Integration

In each `Findings/*.md` file, screenshots are embedded like this:

```markdown
![Proof](../Reports/Screenshots/DOM/dom-xss-popup.png)


** How to Use This Repository
1 Clone the repository: git clone https://github.com/lucky-cyber3008/juice-shop-vapt.git

2 Read vulnerability details in the Findings/ folder.

3 View proof-of-concepts in the linked Screenshots/ subfolders


🙋‍♂️ Author
Lucky
GitHub: lucky-cyber3008

📜 Disclaimer
This project is conducted on OWASP Juice Shop for educational purposes only. Do not attempt these techniques on unauthorized systems.


