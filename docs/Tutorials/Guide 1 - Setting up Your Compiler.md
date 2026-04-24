---
share_cda3103c: "true"
site-folder: docs/Tutorials
---

**📌 PART 1: C DEVELOPMENT ENVIRONMENT (WSL + LINUX)**

To program in C for CDA3103C, you’ll need a Linux environment.

---

**1️⃣ Install WSL (Windows Subsystem for Linux)**

* Open **PowerShell as Administrator**
* Run:

  ```bash
  wsl --install
  ```
* Restart your computer
* Complete the Ubuntu setup (username + password)

---

**2️⃣ Install Build Tools (Compiler + Debugger)**
Open your Ubuntu terminal and run:

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install build-essential gdb -y
```

---

**3️⃣ Install VS Code + Extensions**

* Install **VS Code**
* Add extensions:

  * ✅ WSL Extension
  * ✅ C/C++ Extension Pack

---

**4️⃣ Start Coding 🚀**

* Open your Ubuntu terminal
* Navigate to your folder
* Run:

  ```bash
  code .
  ```
* This launches VS Code connected to Linux

---

**💡 Tip:** Always code inside WSL (Linux), not Windows, for this class.