🦖 ARK Tribe Companion (TEK LOG v1.8.0)
A "Smart Dashboard" for ARK: Survival Ascended. This tool automatically reads your in-game Dino Exports, uploads them to the cloud, and analyzes your breeding lines to tell you exactly what to breed next.

🌟 Key Features
1. 📂 The Library
Auto-Import: Just point your Export Gun at a dino and click "Export." It appears on the website instantly.

Visual DNA: See the exact color regions of every dino visualized as a color bar.

Smart Sorting: Sort by High Stats, Mutation Count, or Name.

The Graveyard: "Soft Delete" dead or sold dinos to hide them from breeding plans without deleting their data (preventing re-upload loops).

2. ❤️ Genetic Strategist (Matchmaker)
Population Census: Automatically detects if you are missing a gender.

Conflict Resolution: Identifies if your best stats are split across same-sex dinos and tells you how to fix it.

Aggressive Math: Prioritizes "Potential" (3 High Stats) over "Safety" (2 Guaranteed High Stats).

Target Lock: Displays the exact stat values you are looking for in a baby.

Endgame Logic: Automatically switches to "Mutation Phase" when you achieve a perfect breeding pair.

3. 🧬 Lineage Tracker
Stat-Specific Tracking: Tracks your HP, Melee, Stamina, and Weight lines separately.

Mutation Deltas: Automatically detects new mutations and highlights them in pink (e.g., Stam: 44 (+2)).

Leaderboard: Shows the current "King" of each stat line.

🛠️ Installation Guide
Prerequisites
ARK: Survival Ascended (Steam Version preferred for easy file access).

Python 3.x installed on your computer.

Google Firebase Account (Free Tier).

Step 1: Firebase Setup
Go to console.firebase.google.com.

Create a new project (e.g., "ArkCompanion").

Build > Firestore Database: Create database (Start in Test Mode).

Project Settings > Service Accounts:

Select "Python".

Click Generate New Private Key.

Save the file as serviceAccountKey.json in your project folder.

Project Settings > General:

Scroll down to "Your Apps" > Click the </> (Web) icon.

Copy the firebaseConfig object.

Paste it into your index.html (replace the existing config).

Step 2: Python Setup
Open your project folder in a terminal.

Install required libraries:

Bash

pip install firebase-admin watchdog
Open auto_uploader.py and edit the EXPORT_FOLDER path to match your PC:

Default: C:\Steam\steamapps\common\ARK Survival Ascended\ShooterGame\Saved\DinoExports\ASB

Step 3: Running the Tool
Start the "Listener":

Bash

python auto_uploader.py
First Run: Type y to scan all existing exports.

Daily Run: Just hit Enter to skip the full scan.

Open the Dashboard:

Double-click index.html to open it in your browser.

🎮 How to Use
Exporting Dinos
In-game, hold the Taxidermy Tool (or Dino Storage Gun if using mods).

Look at a dino.

Select Options > Export Dino.

The Python script will beep/log: [CREATED] Rex (Muts: 2).

The Website will instantly update.

Managing Lines
Check the "Matchmaker" tab: It will tell you which Male and Female to breed.

Claim Babies: When a baby is born, claim it and export it immediately.

Check "Lineage": See if the baby took the "High Stat" title.

Cull/Archive: If the baby is trash, kill it in-game. On the website, click the 💀 (Archive) button to hide it from future plans.

⚠️ Troubleshooting
Q: I deleted a dino on the site, but it came back!

A: Do not use the "Delete" function unless you also delete the file from your hard drive. Instead, use the Archive (💀) button. This keeps the data in the database (preventing re-upload) but hides it from your view.

Q: My mutations aren't showing (+2) in pink?

A: Ensure you are using Python Script v5.0. Older versions did not read the specific stat mutation data from the export file. Run the script and type y to re-process your library.

Q: The site is blank!

A: Check your browser console (F12) for errors. Ensure your firebaseConfig in index.html is correct.
