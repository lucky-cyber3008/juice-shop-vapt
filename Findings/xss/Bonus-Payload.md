# 🎯 Bonus XSS Payload – OWASP Juice Shop

## 🔍 Description

This challenge demonstrates a **non-traditional, bonus XSS payload** in the OWASP Juice Shop application. While it doesn't trigger a classic alert box, it executes a payload using an embedded multimedia iframe, fulfilling the criteria for this hidden challenge.

The challenge involves injecting a **valid SoundCloud iframe** into a search field that gets reflected and rendered, proving the application fails to sanitize embedded HTML.

---

## 🛠️ Steps to Reproduce

1. **Login to Juice Shop**
   - Login as any user (you don’t need to be admin).
   - Example credentials:
     - Email: `user1@juice-sh.op`
     - Password: `password123`

2. **Navigate to the Score Board**
   - Directly open:
     ```
     http://127.0.0.1:4200/#/score-board
     ```
   - Scroll to the **Bonus Payload** challenge under **Cross-Site Scripting (XSS)**.

3. **Copy the Suggested Payload**
   - The challenge provides this payload:
     ```html
     <iframe width="100%" height="166" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/771984076&color=%23ff5500&auto_play=true&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"></iframe>
     ```

4. **Trigger the Vulnerability**
   - Go to the **Search** icon (top right).
   - Paste the entire iframe payload into the search bar and press Enter.

5. **Result**
   - The SoundCloud music player is embedded and plays automatically.
   - The application renders raw HTML inside the DOM without sanitization, proving XSS via embedded media works.

---

## 📸 Screenshot

> 📂 Saved under: `Reports/Screenshots/XSS/Bonus-Paylaod`
