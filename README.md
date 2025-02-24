# 📖 **README - BIP39 Key Generator**

This **BIP39 Key Generator** is a fully client-side web application designed to generate secure, deterministic keys from mnemonic phrases. Users can download and run the single HTML file locally, ensuring privacy and security without relying on external servers.

---

## 🚀 **Features**

- **Secure Local Generation:**  
  No external API calls are made. All key generation processes occur on the user’s device using the browser's native crypto APIs.
  
- **BIP39 Compliance:**  
  Implements the [BIP39 standard](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki) to generate mnemonic phrases and deterministic keys.

- **Two Modes of Generation:**  
  - **Random Generation:** Instantly create a secure, random 12-word mnemonic.  
  - **Manual Selection:** Choose words manually with built-in validation for correct final-word selection.

- **Clipboard Support:**  
  Easily copy generated mnemonics with a single click.

- **Passphrase Support:**  
  Option to include a passphrase for an added layer of security.

---

## 🛡️ **Technical Highlights**

- **Pure HTML/JS with TailwindCSS:**  
  No build tools or frameworks required. Just download and open the file in your browser.

- **Secure Randomness:**  
  Utilizes `crypto.getRandomValues()` for cryptographically secure random number generation.

- **SHA-256 & PBKDF2 via WebCrypto:**  
  - **SHA-256**: Used to derive checksum bits.  
  - **PBKDF2 with SHA-512**: Derives a 512-bit seed from the mnemonic and optional passphrase with 2048 iterations.

- **Checksum Validation:**  
  Automatically ensures that mnemonic words comply with BIP39’s checksum requirements.

- **Mnemonic Wordlist:**  
  Integrated with the standard English BIP39 wordlist for consistency and compatibility.

- **Real-Time Feedback:**  
  - Word selection interface highlights valid/invalid choices.  
  - Instant validation after selecting 12 words.

---

## 📝 **How to Use**

1. **Download the HTML file** and open it in your browser.  
2. **Generate a mnemonic:**  
   - Click "generate mnemonic" for a random 12-word phrase.  
   - OR select "Pick mnemonic" to manually choose words.  
3. **Copy the mnemonic** using the "copy" button for safekeeping.  
4. **(Optional)** Use the mnemonic to derive a seed with or without a passphrase.

---

## ⚙️ **Technical Feats**

- Fully self-contained: No internet connection required once downloaded.  
- Secure random entropy generation ensures robust key security.  
- Comprehensive validation ensures only valid BIP39 mnemonics are generated.  
- Efficient use of WebCrypto API, ensuring modern browser compatibility.  

---

💡 **Disclaimer:**  
Always store your mnemonic phrases securely. Losing them means losing access to associated keys. Never share your mnemonic with untrusted parties.
