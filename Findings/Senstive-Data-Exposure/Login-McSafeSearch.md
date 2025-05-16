# 🔐 Login MC SafeSearch Without SQL Injection – OWASP Juice Shop

## 🧠 Description

This challenge demonstrates the risk of using publicly shared or easily guessable passwords. It emphasizes the importance of keeping authentication secrets confidential and not revealing credentials through public content such as videos, blogs, or social media posts.

---

## 🛠️ Steps to Reproduce

1. **Find Public Clues**
   - Go to Google and search: `MC SafeSearch password site:youtube.com`
   - Locate the music video:  
     🔗 https://imvdb.com/video/mc-safesearch/protect-ya-passwordz

2. **Analyze the Video**
   - At **0:33**, the lyrics mention:
     > “Mine’s my dog, Mr. Noodles. It don’t matter if you know  
     because I was tricky and replaced some vowels with zeroes.”

3. **Derive the Password**
   - Replace vowels with zeroes in the pet's name:
     - `Mr. Noodles` → `Mr.N00dles` (e.g., "o" → "0")

4. **Capture Login Request**
   - Open Juice Shop.
   - Attempt to login with dummy credentials and intercept the request using **Burp Suite**.

5. **Modify the Intercepted Request**
   - Replace the email and password fields as:
     - **Email:** `mc.safesearch@juice-sh.op`
     - **Password:** `Mr.N00dles`

6. **Forward the Request**
   - Forward the modified request.
   - You will successfully log in as **MC SafeSearch**, completing the challenge.

---
## 📸 Screenshot

📁 Navigate to:  
`Reports/Screenshots/Senstive-Data-Exposure`

---
