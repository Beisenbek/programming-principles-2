# TSIS 2: Paint Application — Extended Drawing Tools

## 1. Objective

Extend the Paint application from Practice 10 and Practice 11 by adding freehand drawing, line tools, adjustable brush size, a flood-fill tool, text placement, and canvas saving. The focus is on building a more complete drawing experience using only Pygame's built-in capabilities.

---

## 2. Base (already done in Practice 10–11)

| Done in | Feature |
|---|---|
| Practice 10 | Rectangle, circle, eraser, color picker |
| Practice 11 | Square, right triangle, equilateral triangle, rhombus |

---

## 3. Tasks

### 3.1 Freehand & Line Tools

1. **Pencil tool** — while the mouse button is held down, draw continuously along the cursor path using `pygame.draw.line` between consecutive mouse positions.
2. **Straight line tool** — click to set the start point, drag to the end point, release to draw. Show a live preview while dragging.

---

### 3.2 Brush Size

1. Add **three stroke thickness levels**: small (2 px), medium (5 px), large (10 px).
2. Allow switching between sizes via keyboard shortcuts (e.g. `1`, `2`, `3`) or on-screen buttons in the toolbar.
3. Brush size must apply to: pencil, line, rectangle, circle, and all shapes from Practice 10–11.

---

### 3.3 Fill Tool (Flood-Fill)

Implement a **Flood fill** tool:

1. The user clicks inside a closed region; the tool fills the area with the currently selected color.
2. Implement using over the canvas pixels via `pygame.Surface.get_at()` and `pygame.Surface.set_at()`.
3. The fill must stop at boundaries of a different color (tolerance: exact color match is sufficient).

---

### 3.4 Save Canvas

1. Press `Ctrl+S` to save the current canvas as a `.png` file.
2. Use `pygame.image.save(surface, filename)` — no extra libraries needed.
3. File name should include a timestamp (use Python's `datetime` module) so saves do not overwrite each other.

---

### 3.5 Text Tool

1. The user clicks on the canvas to place a text cursor.
2. Typed characters appear at that position in real time.
3. Press `Enter` to confirm and render the text permanently onto the canvas.
4. Press `Escape` to cancel.
5. Use `pygame.font.SysFont` or `pygame.font.Font` (built-in, no extra libraries).

---

### 3.6 Save to GitHub

Example repository structure:
```
TSIS2/
├── paint.py
├── tools.py
└── assets/
    └── (any icons or fonts if used)
```

---

## 4. What You Must Complete

- ✅ Pencil (freehand) tool
- ✅ Straight line tool with live preview
- ✅ Three brush size levels with keyboard / button toggle
- ✅ Flood-fill
- ✅ `Ctrl+S` saves canvas as timestamped `.png`
- ✅ Text tool: click to place, type, Enter to confirm, Escape to cancel
- ✅ All existing shapes (Practice 10–11) respect the active brush size
- ✅ Push to GitHub with clear commit messages
