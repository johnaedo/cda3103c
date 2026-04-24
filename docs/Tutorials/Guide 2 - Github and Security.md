---
share_cda3103c: "true"
site-folder: docs/Tutorials
---

**📌 PART 2: GITHUB + SECURITY SETUP**

---

**1️⃣ Get GitHub Student Pack 🎓**

* Go to: https://education.github.com/pack
* Sign up using your your-NID@ucf.edu** email

---

**2️⃣ Configure Git Identity (IMPORTANT)**
In your WSL terminal:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-NID@ucf.edu"
```

---

**3️⃣ Generate SSH Key 🔑**
Run:

```bash
ssh-keygen -t ed25519 -C "your-NID@ucf.edu"
```

Press Enter through prompts.

---

**4️⃣ Add SSH Key to GitHub**

* Show your key:

  ```bash
  cat ~/.ssh/id_ed25519.pub
  ```
* Copy the output
* Go to GitHub → **Settings → SSH Keys → New Key**
* Paste and save

---

**💡 Why SSH?**
No passwords needed when pushing code—faster and more secure.