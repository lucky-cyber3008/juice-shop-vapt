# 🧾 Sensitive Data Exposure – Access a Confidential Document | OWASP Juice Shop

## 🔍 Description

**Sensitive Data Exposure** occurs when an application inadvertently reveals confidential information due to improper access control, insecure storage, or insufficient encryption. In this challenge, the Juice Shop exposes a confidential file that should not be accessible to regular users.

This vulnerability can lead to **information disclosure**, **privacy violations**, or **leakage of internal resources** such as admin credentials, private keys, or internal documents.

---

## 🛠️ Steps to Reproduce

1. **Log in to OWASP Juice Shop**
   - Use any valid user account (e.g., `test@juice-sh.op / password123`).

2. **Navigate to the Administration Area**
   - Open the **developer tools (F12)** in your browser.
   - Go to the **Network** tab and start monitoring network activity.

3. **Search for Hidden Endpoints**
   - Visit random paths or analyze the `robots.txt` file by going to:
     ```
     http://<host>/robots.txt
     ```
   - It may contain disallowed directories like:
     ```
     Disallow: /ftp/
     ```

4. **Access the Exposed Directory**
   - Open the listed path (e.g., `/ftp/`) directly in the browser:
     ```
     http://<host>/ftp/
     ```

5. **Download the Confidential File**
   - Inside the `/ftp/` directory, locate a file such as:
     ```
     acquisitions.md
     ```
   - Click to download and view the contents.
   - The file includes sensitive information (e.g., legal disclaimers, internal notes).

---

## 📸 Screenshot

![Sensitive Data Exposure Proof Screenshot]

🔍 *To view this screenshot manually, navigate to:*  
`Reports/ → Screenshots/ → Sensitive-Data/`

📁 Each vulnerability in this project has a **dedicated folder** under `Reports/Screenshots/` for better organization and clarity.
