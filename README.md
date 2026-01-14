# 🦖 ARK Tribe Companion (v1.0.0)

A private automated tool for tracking our tribe's dino stats, genetics, and breeding recommendations.

## 🌟 Features
* **Auto-Upload:** Shoot a dino with the Export Gun mod, and it appears on the site instantly.
* **Cloud Database:** Data is synced between all tribe members.
* **Smart Library:** Sort by HP, Melee, Level, etc.
* **Breeding Advisor:** Automatically finds the best Male/Female pairs for mutations.

---

## 🛠️ Setup (For Tribe Members)

If you want to contribute data (upload dinos), you need to run the Python watcher.

### 1. Prerequisites
1.  **Install Python:** Download and install Python from [python.org](https://www.python.org/).
    * *Important:* Check the box **"Add Python to PATH"** during installation.
2.  **Install Libraries:** Open your Command Prompt (cmd) and run:
    ```bash
    pip install firebase-admin watchdog
    ```

### 2. The Secret Key
You need the `serviceAccountKey.json` file.
* **Do not generate your own.**
* Ask the Admin (me) to send you the file.
* Place it in the **same folder** as the `auto_uploader.py` script.

### 3. Configure Your Path
1.  Right-click `auto_uploader.py` and choose **Edit** (with Notepad or IDLE).
2.  Find the line that says `EXPORT_FOLDER = ...`
3.  Change this path to match **YOUR** computer's Ark export folder.
    * It usually looks like: `C:\Steam\steamapps\common\ARK Survival Ascended\ShooterGame\Saved\DinoExports\ASB`

---

## 🚀 How to Use

### Step 1: Start the Watcher
Double-click `auto_uploader.py`. A black window should appear saying:
> "Watching folder: ... Supports: New Exports & Updates"

**Keep this window open while playing!**

### Step 2: Export In-Game
1.  Equip the **ASB Export Gun**.
2.  Shoot a dino.
3.  Look at the black window—you should see `[CREATED]` or `[UPDATED]`.

### Step 3: View the Data
Go to our Tribe Website URL:
> [INSERT YOUR GITHUB PAGES LINK HERE]

---

## ⚠️ Troubleshooting
* **"Module not found" error?** You didn't run the `pip install` command in Step 1.
* **Script closes immediately?** You might be missing the `serviceAccountKey.json` file, or your folder path is wrong. Open the script in IDLE to see the error message.
