# TSIS 3: Racer Game — Advanced Driving, Leaderboard & Power-Ups

## 1. Objective

Extend the Racer game from Practice 10 and Practice 11 by adding an arcade-style road course with lane hazards, dynamic track events, and player progression. The goal is to make the track itself more interesting with obstacles, moving road features, and clear checkpoints while still keeping leaderboard and settings support.

---

## 2. Base (already done in Practice 10–11)

| Done in | Feature |
|---|---|
| Practice 10 | Player car movement and lane-based road scrolling |
| Practice 10 | Random coins spawning on the road |
| Practice 10 | Coin counter display |
| Practice 11 | Weighted coins with different values |
| Practice 11 | Increasing enemy speed after collecting coins |

**Do not re-implement anything from the list above.**

---

## 3. Tasks

### 3.1 Gameplay & Race Track

1. **Lane hazards and safe paths** — place obstacles, oil spills, or slow-down zones in some lanes so the player must choose the safest path.
2. **Road events** — add occasional dynamic events such as moving barriers, speed bumps, or a nitro boost strip to make the track feel alive.

---

### 3.2 Dynamic Traffic & Obstacles

1. **Traffic cars** — spawn enemy vehicles that move downwards; collisions with traffic end the run.
2. **Road obstacles** — include barriers, oil spills, or potholes that appear randomly and force the player to react.
3. **Safe spawn logic** — ensure new obstacles and traffic do not spawn directly on top of the player.
4. **Difficulty scaling** — increase traffic density and obstacle frequency as the player progresses.

---

### 3.3 Power-Ups and Boosts

Add three collectible power-ups on the road:

| Power-up | Effect | Duration / Rule |
|---|---|---|
| Nitro | Temporarily increases speed | 3–5 seconds |
| Shield | Protects from one collision | until hit |
| Repair | Restores one crash or clears one obstacle | instant |

Rules:
1. Only one power-up can be active at a time.
2. Power-ups disappear after a timeout if not collected.
3. Display active power-up and remaining time on screen.

---

### 3.4 Score, Distance & Leaderboard

1. **Score calculation** — combine collected coins, distance traveled, and bonuses from power-ups.
2. **Distance meter** — show how far the player has driven and the remaining distance to finish.
3. **Leaderboard persistence** — save top scores to a local file such as `leaderboard.json` or `scores.json`.
4. **Username entry** — ask the player for a name before starting the game and use it for leaderboard entries.
5. **Top 10 screen** — show the top scores inside the game with rank, name, score, and distance.

---

### 3.5 Game Screens and Settings

Implement the following Pygame screens without external UI libraries:

1. **Main Menu** — buttons: Play, Leaderboard, Settings, Quit.
2. **Settings screen** — allow toggling sound, selecting car color, and choosing difficulty.
3. **Game Over screen** — show score, distance, coins, and buttons: Retry, Main Menu.
4. **Leaderboard screen** — display saved top 10 scores with a Back button.

Additionally:
- Save settings to `settings.json` and load them at startup.
- Apply saved preferences to the game immediately.

---

### 3.6 Save to GitHub

Example repository structure:
```
TSIS3/
├── main.py
├── racer.py
├── ui.py
├── persistence.py
├── settings.json
├── leaderboard.json
└── assets/
    └── (images, sounds if used)
```

---

## 4. What You Must Complete

- ✅ Lane hazards and dynamic road events
- ✅ Dynamic traffic cars and random road obstacles
- ✅ Three collectible power-ups: Nitro, Shield, Repair
- ✅ Difficulty scaling as the player progresses
- ✅ Persistent leaderboard saved to a local JSON file
- ✅ Username entry and top 10 leaderboard screen
- ✅ Settings screen with sound toggle, car color, and difficulty options
- ✅ Save/load settings via `settings.json`
- ✅ Main Menu, Game Over, Leaderboard, and Settings screens
- ✅ Push to GitHub with clear commit messages
