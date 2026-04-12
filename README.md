# Smiley — The Survival of Smiley

Smiley is a 2D arcade-style, tile-based survival game built in Java. It started as a school project (world generation + rendering), and was extended afterward with rounds, enemies, combat, health, potions, and save/load.

## Gameplay

- You spawn in a procedurally generated world (seeded RNG).
- Enemies (“entities”) hunt you by moving toward your position.
- Survive as many rounds as you can; difficulty increases as more enemies appear.
- Collect health potions to restore HP.

## Controls

**Main menu**
- `N` — New game
- `L` — Load game
- `Q` — Quit

**New game seed entry**
- Type digits `0-9` — Build a seed value
- `S` — Start the game with that seed

**In-game**
- `W` / `A` / `S` / `D` — Move
- `Space` — Attack nearby enemies (adjacent tiles)
- `Q` — Quit + save

## Running the game

### Prereqs

- Java (JDK) installed (Java 11+ recommended)
- The required `.jar` dependencies live in `Library/` (including `algs4.jar` for `StdDraw`).

### Option A: IntelliJ (simplest)

1. Open this folder as a project.
2. Add all `.jar` files in `Library/` to the project’s classpath (Project Structure → Libraries).
3. Run the main class: `src/core/Main.java` (`core.Main`).

### Option B: Command line

**Windows (PowerShell)**

```powershell
$cp = "Library/*"
$src = (Get-ChildItem -Recurse -Filter *.java src | ForEach-Object FullName)
javac -cp $cp -d out $src
java -cp "out;$cp" core.Main
```

**macOS/Linux (bash/zsh)**

```bash
CP="Library/*"
find src -name "*.java" > sources.txt
javac -cp "$CP" -d out @sources.txt
java -cp "out:$CP" core.Main
```

## Save / load

- The game writes your save to `savegame.txt` in the repo root.
- To reset progress, delete `savegame.txt`.

## Project layout

- `src/core/` — Game loop, world logic, entities, audio, save/load
- `src/tileengine/` — Tile + renderer utilities (provided starter code)
- `src/utils/` — Utility helpers
- `resources/` — Extra assets (e.g. `background_music.wav`)
- `SmileyPDFDesignDoc.pdf` / `SmileyDesignDoc.docx` — Design docs

## Notes

- Music playback currently uses a hard-coded local path in `src/core/AudioPlayer.java`. If audio doesn’t play on your machine, update it to a repo-relative path (e.g. `src/music/gg.wav` or `resources/background_music.wav`).


