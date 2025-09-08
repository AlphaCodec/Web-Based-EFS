# 🔐 EFS Explorer

**EFS Explorer** (Encrypted File System Explorer) is a browser-based secure file manager that allows you to **encrypt, store, and manage files directly in your browser**.  
All files are protected using **AES-GCM encryption** with a password-derived key. Nothing leaves your device — everything is handled locally using the Web Crypto API and IndexedDB.

---

## ✨ Features

- **Password-based security**
  - Files are encrypted with AES-GCM.
  - Keys are derived using PBKDF2 with random salt + high iteration count.
  - Password is never stored — you must re-enter it to unlock files.

- **Secure file storage**
  - Files are stored in browser’s IndexedDB.
  - Only ciphertext, salt, IV, and metadata are stored.
  - Even if someone steals the DB, contents remain encrypted.

- **Drag & drop upload**
  - Intuitive drag-and-drop zone with pulsing glow animation.
  - File input button as fallback.

- **File explorer**
  - Lists all stored encrypted files after unlocking.
  - Allows downloading (decrypted) or deleting files.

- **Integrity checking**
  - SHA-256 hash ensures decrypted file matches the original.

- **Reset environment**
  - Reset button wipes all stored files and clears session.
  - 5-second delayed confirmation (Yes/No) to prevent accidents.

- **UI/UX**
  - Clean and lightweight design (HTML + CSS).
  - Smooth animations for drag-over states.
  - Styled confirmation dialogs and buttons.

---

## 🛠️ Technologies Used

- **HTML5 / CSS3 / JavaScript (Vanilla)**
- **Web Crypto API** – AES-GCM, PBKDF2, SHA-256
- **IndexedDB** – Persistent encrypted file storage
- **Blob API** – Secure file download handling

---

## 📂 Project Structure

```
efs-explorer/
│
├── index.html          # Main UI layout
├── style.css           # Lightweight styles, drag-drop animation
│
├── script.js           # App logic (UI, file operations, reset flow)
├── crypto-helper.js    # Encryption/decryption utilities
├── db.js               # IndexedDB wrapper (save/get/delete files)
│
└── README.md           # Project documentation
```

---

## 🚀 How to Run

1. Clone or download this repository.
2. Open `index.html` in a modern browser (Chrome, Firefox, Edge).
3. Set a password to unlock the environment.
4. Drag and drop files to encrypt and store them.
5. To retrieve files:
   - Enter the same password.
   - Select files to download (decrypted).
6. Use **Reset** to wipe everything (irreversible).

---

## ⚠️ Security Notes

- Files are encrypted locally with **AES-GCM**.  
- Passwords are never stored. If forgotten, files **cannot** be recovered.  
- Reset permanently deletes all encrypted data.  
- Browser extensions or keyloggers may compromise security.  
- For maximum security, use strong passwords.

---

## 📸 Demo with Images and Descriptions

## Password Setup Page
<svg width="650" height="700" xmlns="http://www.w3.org/2000/svg">
  <!-- Pulsing animated border -->
  <rect x="5" y="5" width="640" height="690" rx="20" ry="20" fill="none" stroke-width="6">
    <animate attributeName="stroke" values="#2F81F7; #00FFFF; #A020F0; #2F81F7" dur="6s" repeatCount="indefinite"/>
  </rect>

  <!-- Screenshot -->
  <image href="https://github.com/user-attachments/assets/839b9c0a-ec98-475f-bdd9-3accb1beaad8" x="20" y="20" width="610" height="650" />

  <!-- Caption -->
  <text x="50%" y="685" text-anchor="middle" font-size="18" fill="#555" font-family="Arial">
    Starting page for password setup when no files are present in the environment.
  </text>
</svg>


---

## 📌 Future Improvements

- Folder support (virtual directories in IndexedDB).  
- Session auto-lock after inactivity.  
- File preview without full download.  

---

## 📜 License

This project is for **educational purposes** ( Security / Browser Security coursework).  
You may use, modify, and extend it freely.
