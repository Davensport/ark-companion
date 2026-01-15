# 🦖 ARK Tribe Companion (v1.3.2)

The "Go-To" automated tool for The Gooners tribe. Tracks dino stats, calculates breeding scores, and generates step-by-step genetic strategies.

## 🌟 Major Features
* **Auto-Upload:** Shoot a dino with the Export Gun mod, and it appears on the site instantly.
* **Mutation Tracking:** Automatically detects mutation counters.
    * 🟢 **CLEAN:** 0/20 Mutations (Perfect for breeding stock).
    * 🟡 **MUTATED:** 1-19 Mutations.
    * 🔴 **CAPPED:** 20+ Mutations (Cannot trigger new mutations).
* **Genetic Strategist:** The app analyzes your library and tells you exactly how to combine stats (e.g., *"Breed Male A with a clean Female to swap stats, then breed with Male B"*).
* **Smart Scoring:** Calculates a "Breeding Score" based on your selected priorities (HP, Melee, Weight, etc.).

---

## 🛠️ Setup (For Tribe Members)

To upload data, you need the Python "Watcher" script running on your PC.

### 1. Prerequisites
1.  **Install Python:** [Download Here](https://www.python.org/).
    * *Important:* Check the box **"Add Python to PATH"** during installation.
2.  **Install Libraries:** Open Command Prompt (cmd) and run:
    ```bash
    pip install firebase-admin watchdog
    ```

### 2. The Keys
1.  Get the `auto_uploader.py` file from the tribe Discord.
2.  Get the `serviceAccountKey.json` file from the Admin (Dylan).
3.  Put both files in the **same folder** on your computer.

### 3. Configure Path
1.  Right-click `auto_uploader.py` -> **Edit** (Notepad or IDLE).
2.  Change the `EXPORT_FOLDER` line to match your ARK install path:
    * Example: `C:\Steam\steamapps\common\ARK Survival Ascended\ShooterGame\Saved\DinoExports\ASB`

---

## 🚀 How to Use

### 1. The "Backfill" (Updating Old Dinos)
When you first run the script, it will ask:
> "Found 50 existing files. Update them now? (y/n)"
* Type **`y`** and hit Enter.
* This forces the database to re-read all your old exports to grab the latest **Mutation Counts** and **Color IDs**.

### 2. Live Uploading
Keep the black Python window open while you play.
1.  Equip the **ASB Export Gun**.
2.  Shoot a dino.
3.  The script will beep/log: `[UPDATED] Rex -> Muts: 2`.
4.  Refresh the website.

### 3. The "Breeding" Tab
1.  **Select a Species** in the Library first.
2.  Click the **Breeding Tab**.
3.  **Toggle Priorities:** Check the boxes for stats you actually want (e.g., uncheck "Oxygen" for Rexes).
4.  **Read the Strategy Board:**
    * If you see a ⚠️ **WARNING**, follow the numbered steps (e.g., Gender Swap required).
    * If the path is clear, look for the **Best Match** recommendation.

---

## ⚠️ Troubleshooting
* **Script closes instantly?**
    * Open `cmd`, navigate to the folder, and type `python auto_uploader.py` to see the error message.
    * Usually means `serviceAccountKey.json` is missing or your folder path is wrong.
* **"Syntax Error" in Python?**
    * Make sure you didn't accidentally delete a character when editing the folder path.
