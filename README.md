# Web Panel Account Validator

This project automates the login and account validation process for a web panel using Puppeteer (Node.js). It reads a list of account credentials, attempts to log into each one and extracts useful data for valid accounts. If the account level is 20 or higher, the script logs the account credentials into a local file.

## 📌 Features

- Automated login to example website
- Supports CSRF token handling and form submission
- Detects login errors, PIN requirement, and rate limiting
- Scrapes user profile data: Level & Faction Punish
- Saves valid accounts (level ≥ 20) to `valid.txt`
- Handles delays intelligently to avoid triggering bans

---

## 📁 File Structure

```
.
├── checker.js         # Main Puppeteer automation script
├── accounts.txt     # Input file containing raw account credentials
├── valid.txt      # Output file containing valid accounts
```

---

## ⚙️ Prerequisites

- **Node.js** v18+ installed
- Google Chrome installed at:
  ```
  C:\Program Files\Google\Chrome\Application\chrome.exe
  ```

- Required NPM module:
  ```bash
  npm install puppeteer
  ```

- Add this to your `package.json` to support ES modules:
  ```json
  {
    "type": "module"
  }
  ```

---

## 📝 Input Format: `accounts.txt`

Each line should follow this format:
```
:username:password
```

Example:
```
:john_doe:password123
:jane_smith:qwerty456
```

---

## 🚀 Running the Script

```bash
node bhood.js
```

---

## 📤 Output: `valid.txt`

Valid accounts (level ≥ 20) are saved in this format:
```
username/password/
```

Example:
```
john_doe/password123/
```

---

## ❗ Handling Errors

- **Too Many Attempts**: Automatically waits based on the time in the message (e.g., 300 seconds).
- **Incorrect Credentials**: Skips and waits briefly before continuing.
- **PIN Page**: Skips accounts that require PIN login.

---

## 📄 License

This script is for educational purposes only. Use responsibly and ensure compliance with the terms of service of the website.
