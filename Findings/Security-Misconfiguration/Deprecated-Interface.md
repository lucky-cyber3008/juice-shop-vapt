# 🗂️ Deprecated Interface – OWASP Juice Shop

## 🔍 Description

This challenge demonstrates how legacy or **deprecated B2B interfaces**, when not properly decommissioned, can expose the application to vulnerabilities like **XML External Entity (XXE)** attacks. Attackers can exploit these outdated interfaces to access sensitive data or execute unauthorized actions.

---

## 🛠️ Steps to Reproduce

1. **Login with a Registered User**
   - Sign in to OWASP Juice Shop using any valid credentials.

2. **Navigate to the Complaint Submission Form**
   - Go to the **"Complaint"** section in the app.

3. **Prepare a Malicious `payload.xml` File**
   - Create a file named `payload.xml` with the following content:
     ```xml
     <!--?xml version="1.0" ?-->
     <!DOCTYPE replace [<!ENTITY ent SYSTEM "file:////etc/passwd"> ]>
     ```

4. **Submit a Complaint**
   - In the complaint message field, type any message.  
     Example:  
     ```
     Going To Perform B2B Deprecated Interface Challenge
     ```

5. **Upload the Malicious File**
   - Attach and upload the `payload.xml` file using the form.

6. **Submit the Form**
   - After submitting, the deprecated B2B interface processes the XML file and exposes the contents of `/etc/passwd`, completing the challenge.

---
## 📸 Screenshot

![Deprecated Interface Proof]

📁 Screenshot location: `Reports/Screenshots/Security-Misconfiguration`
