# BIP39 Mnemonic Generator: Secure, Single-File HTML Tool with Zero Dependencies

## Motivation
This BIP39 Key Generator embodies a commitment to radical simplicity, security, and self-containment in cryptocurrency tools. In an era where many key generation apps rely on bloated frameworks, external servers, or third-party libraries, this project stands out as a single, standalone HTML file that performs complex cryptographic operations entirely in the browser. No dependencies, no build steps, no network requests everything runs locally using the browser's native WebCrypto API for cryptographically secure randomness, hashing, and key derivation. This design choice eliminates supply-chain attack vectors, reduces the attack surface to a bare minimum, and makes the tool fully auditable at a glance. Hardcore crypto security enthusiasts will appreciate its transparency: you can inspect the entire codebase in one file, verify it against the BIP39 spec, and run it offline without trusting any external entity. It's a testament to what's possible with vanilla JavaScript and modern browser capabilities, proving that robust security doesn't require complexity.

## Features
- **Fully Client-Side and Dependency-Free:** All operations happen in your browser no servers, no APIs, no external libraries. This is a feat of engineering: a single HTML file handles secure random entropy generation, mnemonic creation, checksum validation, and seed derivation using only built-in browser APIs like `crypto.getRandomValues()` for randomness and WebCrypto for SHA-256/PBKDF2. No need for npm, bundlers, or even an internet connection after download.
- **BIP39 Compliance:** Strictly follows the [BIP39 standard](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki) for generating deterministic keys from mnemonic phrases, ensuring compatibility with wallets like Electrum or hardware devices. Supports popular blockchains that use BIP39-derived keys, including Bitcoin, Ethereum, Solana, Cardano, Polkadot, Binance Smart Chain, and many others.
- **Manual Picker Mode:** Interactively select words from the BIP39 wordlist, with real-time guidance on viable checksum words and automatic validation.
- **Copy to Clipboard:** One-click copying for mnemonics and derived private keys (seeds).
- **Passphrase Support:** Optional passphrase for enhanced security during seed derivation.
- **Validation and Feedback:** Built-in checksum checks ensure only valid mnemonics are accepted, with a popup for confirmation and error handling.
- **Offline-First Security:** Ideal for air-gapped environments download once, disconnect, and generate keys without any data leaving your device. This makes it trusted by security purists who demand verifiable, minimalistic tools.

## Technical Highlights
- **Single-File Feat:** Achieving full BIP39 functionality in one file is remarkable no minification tricks or hidden dependencies. The English wordlist is embedded directly in JavaScript, and all logic (from UI to crypto) is self-contained, making it portable and easy to verify.
- **User Interface:** Clean, responsive design with color-coded feedback (e.g., selected words in green, viable checksums in light green). Includes an overlay to prevent background interactions during validation.
- **Edge-Case Handling:** Prevents duplicate word selections, enforces 12-word limits, and provides alerts for invalid choices.

### Secure Randomness and Crypto Primitives
- Leverages `crypto.getRandomValues()` for entropy, ensuring high-quality randomness without external sources.
- Implements SHA-256 for checksums and PBKDF2 (with SHA-512 and 2048 iterations) for seed generation, all via the browser's WebCrypto API.

## How to Use

### Obtain the File
- If viewing this in a browser with the HTML rendered, simply right-click anywhere on the page and select "Save as" to download the complete file as HTML.
- Alternatively, copy the entire HTML code (from `<!DOCTYPE html>` to `</html>`) into a text editor and save it as `bip39-generator.html` (or any name ending in `.html`).

### Run Locally
- Open the saved `.html` file in any modern browser (e.g., Chrome, Firefox, Edge).
- For maximum security, disconnect from the internet or use an air-gapped machine.

### Generate a Key
- Select 12 words from the list.
- As you approach the final word, viable checksum options highlight automatically.
- Once valid, a popup confirms and displays the mnemonic and private key (seed) with copy buttons.
- Use "Start Over" to reset and generate anew.

### Optional Passphrase
- While not directly in the UI, you can derive seeds with a passphrase by integrating the generated mnemonic into compatible wallets.

## Disclaimer
Store your mnemonic phrases securely back them up offline and never share them. This tool generates valid BIP39 mnemonics, but ultimate security depends on your handling. Always verify generated keys in a trusted wallet before use. No warranties provided; use at your own risk.
