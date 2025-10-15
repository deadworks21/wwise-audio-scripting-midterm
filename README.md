# Wwise Audio Scripting Midterm
Midterm project for the **Audio Scripting** course — demonstrating the integration of sound effects and event logic in **Audiokinetic Wwise** for the provided **Cube Sample Game**.

---

## 📜 Project Overview
For this assignment we were given:
- A **stripped-audio build of the Cube sample game** (no sounds implemented),
- A folder of **raw SFX assets** (WAV files for launch bursts, flight loops, impact explosions, ambience, etc.).

Our task was to **author all of the game’s audio behavior inside Wwise** — creating the events, containers, attenuation curves, and other logic required so that the silent Cube build regains full interactive audio once we export the **SoundBanks**.

---

## 🎯 Goals
The full list of required task is documented in
📄 [Task List Cube.xlsx](./Task%20List%20Cube.xlsx)

| Cube Game Calls by Category | Description                          |
| :-------------------------- | :----------------------------------- |
| Defeated_Knight             | Played upon death of enemy character |
| Defeated_Rat                | Played upon death of enemy character |
| Defeated_Rhino              | Played upon death of enemy character |
| Defeated_Goblin             | Played upon death of enemy character |
| Defeated_Player             | Played upon death of enemy character |
| Defeated_Hellpig            | Played upon death of enemy character |
| Defeated_Bauul              | Played upon death of enemy character |
| Defeated_Ogre               | Played upon death of enemy character |
| Defeated_Slith              | Played upon death of enemy character |
| Foot_Slith                  | *(continues in full spreadsheet)*    |

- Re-assemble the provided SFX so that each gameplay action produces the **correct, context-sensitive sound**  
  – e.g. firing the *Ice Gem* plays the correct launch burst, looping flight whoosh, and ends with the ice-impact explosion (rather than an unrelated sound).  
- Script all playback logic strictly in **Wwise** using Events, Random/Sequence Containers, RTPCs, and States — **no code changes in the Cube game**.
- Build and export the **SoundBank** so that the instructor’s silent game build plays all effects exactly as intended when the bank is loaded.

---

## 🛠️ Wwise Authoring Highlights
- **Events:** set up for each action such as `Fire_IceGem_Player`, `Hit_IceGem_Player`, and `End_IceGem_Player`.
- **Containers:**  
  - Random containers for variation (e.g. multiple gem-break SFX),  
  - Sequence containers to control ordered playback of head / tail layers.  
- **Attenuation curves:** custom distance-volume and LPF settings for spatial realism.  
- **Property containers:** used to group related layers (e.g. all Ice-magic elements share the same reverb send and mix offset).
- **Soundcaster testing:** used in Wwise to audition launch/impact events before exporting.

---

## 📂 Repository Contents
- `/ProjectRoot` – the full Wwise project folder (`.wproj`, Originals, Work Units, etc.).  
- `.gitignore` – excludes generated SoundBanks, cache and temp files.  
- `README.md` – this document.

*(Raw audio and Cube-sample assets are included only for coursework and are **not licensed for redistribution**.)*

---

## 🚀 Usage
1. Open the project in **Wwise** (same version as used in class).  
2. Generate the SoundBanks (`F7` or **Generate All**).  
3. Copy the generated banks into the instructor-provided Cube build’s `GeneratedSoundBanks` folder.  
4. Run the Cube game build — gameplay actions will now trigger the correct sounds.

---

## ⚖️ License & Credits
- **Coursework only:** Audio files and the Cube Sample Game belong to the course/instructor and are not open-licensed.  
- Integration logic and project organization were authored by *\<Your Name\>* as part of the **Audio Scripting Midterm**.

---
