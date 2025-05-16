# 🎯 NFT Takeover – OWASP Juice Shop

## 🔍 Description

This challenge involves taking over a wallet that contains the official Soul Bound Token (NFT) of OWASP Juice Shop. It demonstrates how sensitive information leakage through images and improper handling of wallet credentials can lead to serious security breaches.

---

## 🛠️ Steps to Reproduce

1. **Visit the "About Us" Page**
   - Navigate to the Juice Shop's **About Us** section.

2. **Analyze Embedded Images**
   - Inspect the images shown in the reviews and staff sections using **Developer Tools (F12)**.
   - In one of the images, the following sensitive information is found:
     ```
     Please send me the juicy chatbot NFT in my wallet at /juicy-nft : 
     "purpose betray marriage blame crunch monitor spin slide donate sport lift clutch" 
     (***ereum@juice-sh.op)
     ```

3. **Extract the Mnemonic Phrase**
   - Copy the 12-word mnemonic phrase from the image.

4. **Convert Mnemonic to Private Key**
   - Go to [https://iancoleman.io/bip39/](https://iancoleman.io/bip39/)
   - Paste the mnemonic phrase into the **BIP39 Mnemonic** field.
   - Change the **Coin** from `Bitcoin` to `Ethereum`.
   - A corresponding Ethereum private key will be generated.

5. **Use Private Key to Access the Wallet**
   - Visit `http://127.0.0.1:4200/#/juicy-nft` (or your Juice Shop instance URL + `/juicy-nft`)
   - Enter the generated Ethereum private key when prompted.

6. **Challenge Solved**
   - Upon successful validation of the key, the challenge is marked as complete.

---
## 📸 Screenshot

> 📂 `Reports/Screenshots/SensitiveDataExposure/`

---
