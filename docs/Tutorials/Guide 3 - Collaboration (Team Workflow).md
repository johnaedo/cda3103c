---
share_cda3103c: "true"
site-folder: docs/Tutorials
---

**📌 PART 3: TEAMWORK + GIT WORKFLOW**

---

**1️⃣ Project Setup**

* Team leader creates a GitHub repo
* Invite teammates as collaborators
* Teammates clone the repo:

  ```bash
  git clone <repo-url>
  ```

---

**2️⃣ Create a .gitignore File 🚫**
Inside your repo, create `.gitignore` and add:

```
*.o
a.out
.vscode/
```

This prevents unnecessary files from being uploaded.

---

**3️⃣ Basic Workflow (VERY IMPORTANT)**

✔ **Always follow this order:**

1. Pull latest changes:

   ```bash
   git pull
   ```

2. Make your changes

3. Commit your work:

   ```bash
   git add .
   git commit -m "Describe your changes"
   ```

4. Push to GitHub:

   ```bash
   git push
   ```

---

**⚠️ Golden Rule:**
👉 ALWAYS **pull before you start working**
(prevents conflicts and broken code)

---

**💡 Tip:**
Use VS Code’s **Source Control tab** if you prefer a UI instead of commands.