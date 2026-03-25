[🇹🇷 Click here for Turkish](README.tr.md)

# NEURO-MAZE: Logic Core

A cyberpunk-themed, browser-based 3D pipe-routing puzzle game. Built as a single-page HTML application featuring a Three.js 3D engine, neon visuals, and smooth animations.

---

## Features

### 1. 3D Game Board
- A **6×6×6** three-dimensional grid rendered with **Three.js**
- Freely rotatable camera using **OrbitControls** (drag, zoom, pan)
- Neon-coloured block meshes with emissive glow effects
- Ghost preview block shown while hovering over placement positions

### 2. Block Types
| Block | Colour | Description |
|---|---|---|
| **STRAIGHT** (Straight Pipe) | 🔵 Neon Blue | Passes the signal straight through; supports vertical, horizontal-X, and horizontal-Z orientations |
| **CORNER** (Right-Angle Elbow) | 🟣 Neon Purple | Redirects the signal 90° vertically or horizontally; supports 8 rotations (4 × flip) |
| **TURNER** (Horizontal Elbow) | 🟢 Neon Green | Works only on the horizontal plane; bends the signal left or right; 4 rotations |
| **OMNI** (Omni Hub) | 🟡 Neon Gold | Passes the signal straight through in any direction; acts as a universal bridge |

### 3. Signal Simulation
- A **signal ball** drops from the start marker (cyan wireframe cone) toward the red end marker
- The ball travels cell by cell through the placed blocks
- Fails with **SIGNAL LOSS** if the ball leaves the grid, or **WRONG ROUTE** if a block cannot redirect it
- **All inventory blocks must be placed** before the simulation can start

### 4. Attempt System & SOLUTION Button
- Each level starts with **3 attempts**
- The **🔒 SOLUTION** button unlocks after all attempts are used
- Clicking SOLUTION reveals the correct block layout step by step with animations
- Attempts become **∞** and the RUN button changes to **▶ WATCH** mode

### 5. Controls Panel
- **✖ DELETE** — click any placed block to remove it and return it to inventory
- **Inventory buttons** — select the block type to place; badge shows remaining count
- **⟳ ROTATE** — cycles through 8 rotation states for the selected block
- **▶ START** — launches the simulation (active only when all blocks are placed)
- **🔒 SOLUTION** — reveals the solution (unlocks after attempts run out)

### 6. 10 Progressive Levels
| Level | Name | Description |
|---|---|---|
| 1 | Basic Pass | Route the signal down and to the right |
| 2 | Horizontal Turn | Green TURNER blocks work only on the flat plane |
| 3 | Magic Hub | OMNI blocks pass the signal straight through |
| 4 | Height Difference | Use corner blocks cleverly to descend to lower layers |
| 5 | Spiral Ramp | Sharp manoeuvres both vertically and horizontally |
| 6 | Locked Point | You must pass through the fixed grey blocks in the middle |
| 7 | Zigzag Route | Weave snake-like along the ground floor |
| 8 | Staircase System | Descend floor by floor using only corner blocks |
| 9 | U-Turn | Return parallel to the path you came from |
| 10 | FINAL | Combine everything you know in one massive bridge |

### 7. Block Tutorial Modal
- An interactive **3D block viewer** is shown at startup
- Navigate between block types with ◀ / ▶ buttons; the block rotates automatically
- Block name, colour, and description are displayed
- Re-accessible at any time via the **?** button in the top-right corner

### 8. Info Panel
- **STATUS** — displays READY / SIMULATION… / SIGNAL LOSS / WRONG ROUTE
- **ATTEMPTS** — shows remaining attempts (or ∞ in solution mode)
- **MISSION** — shows the hint text for the current level

### 9. Level Jump
- A dropdown in the header lets you jump directly to any level

### 10. Sound Effects
- Procedural audio via the **Web Audio API** (no external files required)
- Distinct sounds for: place, rotate, win, fail/error, move, start

### 11. Background Music
- Loops `suspence-music-1-8160.mp3` at low volume on game start
- Plays automatically; browser autoplay policy may require user interaction first

### 12. Cyberpunk Visual Theme
- Deep dark background (`#050505`) with exponential scene fog
- Neon blue (`#00f3ff`), purple (`#bc13fe`), green (`#00ff41`), gold (`#ffd700`) colour palette
- Glassmorphism info panel with `backdrop-filter: blur`
- Elastic / bounce / back easing animations via **Tween.js**
- **Exo 2** font from Google Fonts

### 13. Win & Final Screens
- **SUCCESSFUL** modal appears when a level is completed
- **NEURO-MASTER** full-screen overlay fades in after all 10 levels are cleared

---

## Project Structure
neuro_maze/ 
    ├── index.html — full application (HTML/CSS/JS in a single file) 
    └── suspence-music-1-8160.mp3 — background music


---

## Getting Started

    1. Clone the repository:
    ```bash
    git clone https://github.com/miyigun/neuro_maze.git

    2. Enter the project folder:
        cd neuro_maze

    3. Open index.html in your browser — no build step or server required.

## How To Play

    1. Read the block types in the tutorial modal and click START SYSTEM.
    2. Select a block type from the inventory panel at the bottom.
    3. Hover over the 3D grid to see a ghost preview, then click to place the block.
    4. Use ⟳ ROTATE to change the block's orientation before placing.
    5. Use ✖ DELETE mode to remove a misplaced block (it returns to your inventory).
    6. Once all blocks are placed, click ▶ START to launch the simulation.
    7. Watch the signal ball travel through your pipeline — reach the red end marker to win!
    8. If you run out of attempts, the 🔒 SOLUTION button unlocks to show you the answer.


🛠️ Technologies Used

    - HTML5 / CSS3 / Vanilla JavaScript
    - Three.js r128 — 3D rendering engine
    - OrbitControls — camera control
    - Tween.js 18.6.4 — animation easing
    - Google Fonts — Exo 2
    - Web Audio API — procedural sound effects

📌 Notes

    - No installation or build tools needed — just open index.html.
    - All game logic, rendering, and UI are contained in a single index.html file.
    - Background music requires browser autoplay permission; it starts automatically once you interact with the page.
    - The camera can be rotated (drag), zoomed (scroll), and panned (right-click drag) freely around the 3D grid.
    - Fixed grey blocks (level 6) cannot be moved or deleted.

📜 License

    This project is licensed under the MIT License. See the LICENSE file for details.