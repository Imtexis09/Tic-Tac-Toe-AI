# Tic-Tac-Toe AI 🎮🤖

A modern, highly polished clone of the classic *Tic-Tac-Toe* game developed in **C++** using the **SFML** (Simple and Fast Multimedia Library). The project features a dynamic graphical interface, a robust audio management system, and an AI opponent with multiple difficulty levels.

---

## ✨ Key Features

* **Robust State Machine:** Fluid screen transitions managed via structured state control (`Menu`, `Game`, `GameOver`, `Settings`, `ModeSelect`, `DifficultySelect`).
* **Game Modes:**
    * **1 vs 1:** Classic local multiplayer mode for two players.
    * **vs AI:** Challenge the computer, powered by modular decision-making logic.
* **Adjustable Difficulty:** Three AI levels (`Easy`, `Medium`, and `Hard`) that modify its behavioral patterns and decision accuracy.
* **Polished UI/UX:**
    * Real-time calculated dynamic gradient backgrounds.
    * Advanced visual effects, including drop shadows on `X` and `O` game pieces.
    * Animated, stylized winning line with golden borders calculated dynamically using mathematical functions (`std::hypot`, `std::atan2`).
    * Interactive buttons featuring visual and auditory hover effects.
* **Integrated Audio Manager (`AudioManager`):** * Looping background music (`.ogg`).
    * Independent sound effects (`.wav`) for clicks, movements, wins, draws, and hover events.
    * Dedicated audio settings panel to mute or regulate music and sound effects (SFX) volume independently.

---

## 🛠️ Tech Stack

* **Language:** C++17 (or higher)
* **Graphics & Multimedia Library:** [SFML 2.6+](https://www.sfml-dev.org/) (Modules: Graphics, Audio, Window, System)
* **AI Logic:** Deterministic evaluation and search algorithms integrated within `IA.hpp` for game-state assessment.

---

## 🎮 Game Controls

* **Left Click:** Interact with menus, select options, and place your piece (`X` or `O`) on the board.
* **Right Click:** Instantly return to the Main Menu from any secondary screen (Settings, Mode Selection, Difficulty).

---

## 💻 Compilation and Installation

### Prerequisites
Ensure you have a C++17 compatible compiler installed (such as `GCC`/`MinGW` or `MSVC`) and the **SFML** library configured in your system environment variables or IDE.

### Clone the Repository
`git clone [https://github.com/Imtexis09/Tic-Tac-Toe-AI.git](https://github.com/Imtexis09/Tic-Tac-Toe-AI.git)
cd Tic-Tac-Toe-AI`
### Terminal Compilation (Using MinGW/GCC)
Make sure to properly link all SFML dependencies (graphics, window, audio, system):
```bash
g++ -c main.cpp -I"C:\Path\To\SFML\include"
g++ main.o -o tic_tac_toe -L"C:\Path\To\SFML\lib" -lsfml-graphics -lsfml-window -lsfml-audio -lsfml-system
```

---

## 📋 Asset Resource Note
The game searches for audio files in the following relative paths by default:
* `sounds/background.ogg`
* `sounds/click.wav`, `sounds/move.wav`, `sounds/win.wav`, `sounds/draw.wav`, `sounds/hover.wav`
    
Ensure the `sounds/` directory remains in the same folder as your final executable to prevent console asset-loading warnings.

---

## 📐 Technical Architecture Details
The codebase showcases software design best practices applied to native game development:

* **Audio Decoupling:** Using `sf::SoundBuffer` and `sf::Sound` separately prevents memory overhead by reusing audio buffers for repetitive sounds (such as hover or move events) instead of reloading them into memory.
* **Vectorial Logic:** Calculations for the winning line's rotation and length are dynamically performed using pure trigonometry based on the fixed window resolution (700 x 700 pixels).
