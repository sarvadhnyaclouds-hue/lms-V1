# DjangoLMS - Library Management System — Installation Guide

> **Support:** sarvadhnyaclouds@gmail.com
> **Supported Windows:** Windows 7 · Windows 8 · Windows 10 · Windows 11

---

## What You Need

- A Windows PC (7, 8, 10, or 11)
- Internet connection (only for first-time setup)
- Python 3.10 — **free download, explained below**


---

## Step 1 — Download Python 3.10

1. Open your browser and go to:
   **https://www.python.org/downloads/release/python-3100/**

2. Scroll down to the **Files** section at the bottom of the page.

3. Download the correct file for your Windows:

   | Your Windows | File to Download |
   |---|---|
   | Windows 10 / 11 (64-bit) | `Windows installer (64-bit)` |
   | Windows 7 / 8 / 10 (32-bit) | `Windows installer (32-bit)` |

   > **Not sure if 32-bit or 64-bit?**
   > Right-click **My Computer** → **Properties** → look for "System type".

---

## Step 2 — Install Python 3.10

1. Double-click the downloaded file (e.g. `python-3.10.0-amd64.exe`).

2. **VERY IMPORTANT — before clicking Install:**

   ✅ Tick the checkbox **"Add Python 3.10 to PATH"** at the bottom of the screen.

   > If you miss this step, the app will not start. You will need to uninstall Python and reinstall.

3. Click **"Install Now"**.

4. Wait for the installation to finish (~1–2 minutes).

5. Click **"Close"**.

6. **Verify Python is installed correctly:**
   - Press `Windows key + R`, type `cmd`, press Enter.
   - In the black window, type:
     ```
     python --version
     ```
   - You should see: `Python 3.10.x`

   If you see an error, see **[Troubleshooting → Python not found](#python-not-found)** below.

---

## Step 3 — Get the Application

1. You will receive a **ZIP file** (e.g. `django_lms_sharepack.zip`).

2. Right-click the ZIP file → **Extract All** → choose a folder (e.g. `C:\LibraryMS`).

3. Open the extracted folder. You should see these files inside:
   ```
   start.bat
   run.py
   requirements-local.txt
   SHARING_README.txt
   apps/
   config/
   templates/
   static/
   ```

---

## Step 4 — Start the Application

1. Inside the extracted folder, **double-click `start.bat`**.

2. A black terminal window will open. **Do not close it.**

3. **First run only** — it will say:
   ```
   Installing packages — first run only, takes ~1-2 minutes …
   ```
   Wait for it to finish. This only happens once.

4. After setup, you will see something like:
   ```
   ══════════════════════════════════════════════
     ✅  LibraryMS is starting …
     ──────────────────────────────────────────
     💻 Local  →  http://127.0.0.1:8000
     📡 LAN    →  http://192.168.1.5:8000
     ──────────────────────────────────────────

   ```

5. Open your browser and go to:
   **http://127.0.0.1:8000**

6. The Library Management System will load. ✅

---

## Step 5 — Sharing with Others

### Same Wi-Fi / Office Network (LAN)
- Share the **LAN link** shown in the terminal (e.g. `http://192.168.1.5:8000`)
- Anyone connected to the **same Wi-Fi or LAN cable** can open this link on their device


---

## Step 6 — Stopping the Application

- Go to the black terminal window
- Press **Ctrl + C**
- The server and the public link will both stop

---

## Troubleshooting

### Python not found

**Error:** `'python' is not recognized as an internal or external command`

**Fix:**
1. Uninstall Python from **Control Panel → Programs → Uninstall a program**
2. Reinstall Python 3.10 from **https://www.python.org/downloads/release/python-3100/**
3. On the installer screen, make sure **"Add Python 3.10 to PATH"** is ticked ✅
4. Restart your PC after installing
5. Try again

---

### Wrong Python version

**Error:** `ERROR: This project supports only Python 3.7 to 3.10`

**Fix:**
- You have Python 3.11 or newer installed.
- Download and install Python **3.10** specifically:
  **https://www.python.org/downloads/release/python-3100/**
- You can keep both versions installed. The app will automatically use 3.10.

---

### Port already in use

**Error:** `Error: That port is already in use`

**Fix:**
1. Open `run.py` in Notepad
2. Find the line: `PORT = "8000"`
3. Change it to: `PORT = "8080"` (or any other number like 8001, 9000)
4. Save the file and run `start.bat` again
5. Open **http://127.0.0.1:8080** in your browser (use your new port number)

---

### LAN link not working on another device

**Possible reasons and fixes:**

1. **Not on the same network**
   - Make sure both devices are connected to the same Wi-Fi router or network cable.

2. **Windows Firewall is blocking**
   - When you first run `start.bat`, Windows may show a popup asking to allow Python through the firewall.
   - Click **"Allow access"**.
   - If you missed it:
     1. Open **Control Panel → Windows Defender Firewall → Allow an app through firewall**
     2. Click **"Change settings"** → **"Allow another app"**
     3. Browse to your `.venv\Scripts\python.exe` inside the app folder
     4. Add it and click OK

3. **LAN IP changed**
   - If you restart your router, your LAN IP may change.
   - Simply restart `start.bat` and check the new LAN link shown.

---


### Packages failed to install

**Error during first run:** `ERROR: Could not install packages`

**Fix:**
1. Check your internet connection
2. Delete the `.venv` folder inside the app folder
3. Run `start.bat` again — it will reinstall everything fresh

---

### App opens but shows a blank/error page

**Fix:**
1. Close the terminal window (press Ctrl+C first)
2. Delete `local_db.sqlite3` from the app folder
3. Run `start.bat` again — a fresh database will be created automatically

---

### Antivirus blocking the app

Some antivirus software may block Python scripts.

**Fix:**
1. Add the app folder to your antivirus **exclusion/whitelist** list
2. Common antivirus steps:
   - **Windows Defender:** Settings → Virus & threat protection → Exclusions → Add folder
   - **Quick Heal / K7 / Avast:** Open antivirus → Settings → Exclusions → Add folder

---

## Windows Version Notes

| Windows | Python Install |  Notes |
|---|---|---|---|
| **Windows 11** | Works normally | ✅ Built-in | No extra steps |
| **Windows 10** | Works normally | ✅ Built-in | No extra steps |
| **Windows 8 / 8.1** | Works normally | ⚠️ Not built-in | Install OpenSSH manually for public link |
| **Windows 7** | Works normally | ⚠️ Not built-in |

> **Windows 7 users:** Make sure Service Pack 1 is installed.
> Go to **Control Panel → System** and check "Service Pack 1" is listed.

---

## Daily Usage

| Task | What to do |
|---|---|
| Start the app | Double-click `start.bat` |
| Open in browser | Go to `http://127.0.0.1:8000` |
| Share with LAN users | Give them the LAN link shown in terminal |
| Stop the app | Press `Ctrl + C` in the terminal |
| Backup data | Copy `local_db.sqlite3` to a safe location |
| Fresh database | Delete `local_db.sqlite3` and restart |
| Reinstall packages | Delete `.venv` folder and restart |

---

## Need Help?

If you face any issue not listed here, contact:

📧 **sarvadhnyaclouds.in**
📧 **sarvadhnyaclouds@gmail.com**

Please include:
- Your Windows version (7 / 8 / 10 / 11)
- A screenshot of the error message
- What step you were on when the error happened

---

*DjangoLMS — Edition*
