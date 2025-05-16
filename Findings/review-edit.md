# ⭐ Remove the Five-Star Feedback – OWASP Juice Shop

## 🔍 Description

This challenge involves locating and removing a specific five-star feedback left by the administrator. It demonstrates an attack path where unauthorized users with admin credentials can access hidden administration features and manipulate data not exposed through the regular UI.

---

## 🛠️ Steps to Reproduce

1. **Login as Admin**
   - Use the provided credentials:
     ```
     Email: admin@juice-sh.op
     Password: admin123
     ```
   - Successfully log in as an administrator.

2. **Inspect JavaScript for Admin Route**
   - Open **Developer Tools** in your browser (F12).
   - Navigate to the **Sources** tab.
   - Search within `main.js` using **Ctrl+F** or **Cmd+F** for the keyword:
     ```
     administration
     ```
   - You’ll find a line like:
     ```javascript
     path: 'administration', component: AdministrationComponent
     ```

3. **Manually Access the Admin Panel**
   - Go to:
     ```
     http://127.0.0.1:4200/#/administration
     ```
   - This reveals a hidden admin dashboard, not accessible through the normal UI.

4. **Review Feedback Ratings**
   - In the admin panel, look for the **Customer Feedback** section.
   - Scroll through the list of feedback.
   - Locate the one left by **admin@juice-sh.op** with a 5-star rating.

5. **Delete the Feedback**
   - Click the **trash/delete icon** next to the 5-star feedback.
   - A confirmation appears, and upon deletion, the challenge is marked as solved.


## 📸 Screenshot

![Review-Edit Proof]

🔍 *To view this screenshot manually, navigate to:*  
`Reports/ → Screenshots/ → /Broekn-Acces-Control

📁 Each vulnerability in this project has a **dedicated folder** under `Reports/Screenshots/` for better organization and clarity.
