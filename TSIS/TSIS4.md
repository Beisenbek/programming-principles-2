# TSIS 4: Snake Game — Database Integration & Advanced Gameplay

## 1. Objective

Extend the Snake game from Practice 10 and Practice 11 by connecting it to a PostgreSQL database for persistent leaderboards, introducing new food behaviors, power-ups, in-game obstacles, and polished game screens — all using only Pygame and psycopg2.

---

## 2. Base (already done in Practice 10–11)

| Done in | Feature |
|---|---|
| Practice 10 | Wall / border collision detection |
| Practice 10 | Random food placement (avoids walls and body) |
| Practice 10 | Level progression (every N food items) |
| Practice 10 | Speed increase per level |
| Practice 10 | Score and level display |
| Practice 11 | Food with different point weights |
| Practice 11 | Food that disappears after a timer |

---

## 3. Tasks

### 3.1 Leaderboard (PostgreSQL + psycopg2)

Integrate the game with a PostgreSQL database to persist player results.

1. **Username entry** — on the main menu screen, prompt the player to enter a username (typed via keyboard in Pygame).
2. **Save result** — after game over, automatically save `username`, `score`, `level_reached`, and `timestamp` to the database.
3. **Leaderboard screen** — fetch and display the Top 10 all-time scores inside the game window.
4. **Personal best** — fetch the player's best score at game start and display it during gameplay.

Suggested schema:
```sql
CREATE TABLE players (
    id       SERIAL PRIMARY KEY,
    username VARCHAR(50) UNIQUE NOT NULL
);

CREATE TABLE game_sessions (
    id            SERIAL PRIMARY KEY,
    player_id     INTEGER REFERENCES players(id),
    score         INTEGER   NOT NULL,
    level_reached INTEGER   NOT NULL,
    played_at     TIMESTAMP DEFAULT NOW()
);
```

---

### 3.2 Poison Food

Add a **poison food** item (distinct color, e.g. dark red) as a new food behavior on top of the existing weighted/disappearing foods from Practice 11:

- Appears randomly on the field alongside normal food.
- If the snake eats it: **shorten the snake by 2 segments**.
- If the snake's length drops to 1 or less after eating poison → **game over**.

---

### 3.3 Power-ups

Spawn temporary power-up items on the field:

| Power-up | Effect | Duration |
|---|---|---|
| Speed boost | Increases snake speed | 5 seconds |
| Slow motion | Decreases snake speed | 5 seconds |
| Shield | Ignores the next wall or self-collision once | Until triggered |

Rules:
- Only one power-up active on the field at a time.
- Each power-up disappears from the field after **8 seconds** if not collected.
- Use `pygame.time.get_ticks()` to track durations.

---

### 3.4 Obstacles

Starting from **Level 3**, static wall blocks appear inside the arena:

1. Randomly place a set of wall blocks at each new level.
2. Guarantee that the blocks do not surround or trap the snake's current position at spawn time.
3. Collision with an obstacle block → **game over** (same as border collision).
4. Food and power-ups must not spawn on obstacle blocks.

---

### 3.5 Settings (JSON file)

Save and load user preferences from a local `settings.json` file using Python's built-in `json` module:

| Setting | Options |
|---|---|
| Snake color | any RGB value |
| Grid overlay | on / off |
| Sound | on / off |

Settings are loaded on startup and saved when the user changes them in the Settings screen.

---

### 3.6 Game Screens

Implement the following screens using Pygame (no external UI libraries):

1. **Main Menu** — buttons: Play, Leaderboard, Settings, Quit.
2. **Game Over screen** — shows final score, level reached, personal best; buttons: Retry, Main Menu.
3. **Leaderboard screen** — table with rank, username, score, level, date; button: Back.
4. **Settings screen** — toggle grid, toggle sound, pick snake color; button: Save & Back.

---

### 3.7 Save to GitHub

Example repository structure:
```
TSIS3/
├── main.py
├── game.py
├── db.py
├── settings.json
├── config.py
└── assets/
    └── (sounds, images if any)
```

---

## 4. What You Must Complete

- ✅ PostgreSQL schema: `players` and `game_sessions` tables
- ✅ Username entry on the main menu
- ✅ Auto-save result to DB after game over
- ✅ Leaderboard screen showing Top 10 from DB
- ✅ Personal best displayed during gameplay
- ✅ Poison food: shortens snake; game over if too short
- ✅ Three power-ups with timed effects (`pygame.time.get_ticks()`)
- ✅ Obstacle blocks from Level 3, randomly placed without trapping snake
- ✅ `settings.json` for snake color, grid, and sound preferences
- ✅ Four game screens: Main Menu, Game Over, Leaderboard, Settings
- ✅ Push to GitHub with clear commit messages