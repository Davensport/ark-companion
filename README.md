# 🦕 ARK Tribe Companion (TEK LOG v1.8.0)

The "Go-To" automated tool for The Gooners tribe. Tracks dino stats, calculates breeding scores, and generates step-by-step genetic strategies.

## 🌟 Major Features

* **Auto-Upload:** Shoot a dino with the Export Gun mod, and it appears on the site instantly.
* **The Graveyard (New!):** "Soft Delete" dead or sold dinos to hide them from breeding plans without breaking your database history.
    * 💀 **Archive Button:** Sends dinos to the graveyard.
    * ♻ **Restore:** Bring them back if you made a mistake.
* **🧬 Lineage Tracker (New!):** A dedicated dashboard that tracks your specific stat lines separately.
    * **Leaderboard:** Automatically finds the "King" of your HP Line, Melee Line, etc.
    * **Mutation Deltas:** Clearly shows exactly how many points a mutation added (e.g., `HP: 50 (+2)`).
* **Genetic Strategist (Matchmaker):** The app analyzes your library and tells you exactly how to combine stats.
    * **Target Lock:** Displays the exact goal stats you are looking for in a baby.
    * **Endgame Logic:** Automatically switches to "Mutation Phase" when you achieve a perfect pair.
* **Smart Sorting:** Sort by High Stats, Mutation Count, or Name.

---

## 🛠️ Setup (For Tribe Members)

To upload data, you need the Python "Watcher" script running on your PC.

### 1. Prerequisites

1.  **Install Python:** [Download Here](https://www.python.org/downloads/).
    * *Important:* Check the box **"Add Python to PATH"** during installation.
2.  **Install Libraries:** Open Command Prompt (cmd) and run:
    ```bash
    pip install firebase-admin watchdog
    ```

### 2. The Keys

1.  Get the `auto_uploader.py` file (v5.0) from the tribe Discord.
2.  Get the `serviceAccountKey.json` file from the Admin.
3.  Put **both files** in a folder on your desktop (e.g., `ArkCompanion`).

### 3. Configure Path

1.  Right-click `auto_uploader.py` -> **Edit** (Notepad or IDLE).
2.  Change the `EXPORT_FOLDER` line to match your ARK install path:
    * *Example:* `C:\Steam\steamapps\common\ARK Survival Ascended\ShooterGame\Saved\DinoExports\ASB`

---

## 🚀 How to Use

### 1. The "Backfill" (Updating Old Dinos)

When you first run the script (after updating to v5.0), it will ask:

> "Found 50 existing files. Update them now? (y/n)"

* Type **`y`** and hit Enter.
* This forces the database to re-read all your old exports to grab the latest **Mutation Deltas** and **Colors**.

### 2. Live Uploading

Keep the black Python window open while you play.

1.  Equip the **ASB Export Gun**.
2.  Shoot a dino.
3.  The script will beep/log: `[CREATED] Rex -> Muts: 2`.
4.  Refresh the website.

### 3. The "Lineage" Tab

1.  Click the **Lineage** tab to see your progress.
2.  It will show you the current **Highest Stat** for HP, Melee, Stamina, and Weight.
3.  Use this to verify if a new baby is actually an improvement.

### 4. Managing Deaths (The Graveyard)

* **If a dino dies:** Do not delete the file. Go to the website and click the **💀 (Archive)** button.
* **Why?** This hides it from the breeding planner but keeps the data safe so the script doesn't try to re-upload it later.
* **To View Dead Dinos:** Click the **💀 SHOW GRAVEYARD** button in the Library.

---

## ⚠️ Troubleshooting

**Q: I deleted a dino on the site, but it came back!**
* **A:** Do not use the "Delete" function unless you also delete the file from your hard drive. Instead, use the **💀 Archive** button. This keeps the data in the database (preventing re-upload) but hides it from your view.

**Q: My mutations aren't showing `(+2)` in pink?**
* **A:** Ensure you are using **Python Script v5.0**. Older versions did not read the specific stat mutation data from the export file. Run the script and type `y` to re-process your library.

**Q: The site is blank!**
* **A:** Check your browser console (F12) for errors. Ensure your `firebaseConfig` in `index.html` is correct.
