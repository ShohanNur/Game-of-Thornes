# Game of Thrones Maze Game (Java FX 17) 🐉⚔️

> A mini **Java FX** desktop game inspired by *Game of Thrones* where you navigate Daenerys through a 6×6 maze while an animated main‑menu and background soundtrack set the mood.

---

## 🚀 Features
- **Interactive Maze Gameplay**  
  * Move **Up / Down / Left / Right** with the keyboard (`U`, `D`, `L`, `R`) to reach the exit.  
  * Collision detection prevents walking through walls.
- **Cinematic Main Menu**  
  Animated fade/slide transitions (`GameMenu.java`) with sub‑menus for *New Game*, *Resume*, *Options*, and *Exit*.
- **Rich Media**  
  *PNG* sprites, *JPEG* backgrounds and looping **MP3** soundtrack via `MediaPlayer`.
- **Customisable Levels**  
  Maze layouts loaded from plain‑text files (`path1.txt`). Add more `pathN.txt` files to create extra stages.
- **Modern Java 17 Tooling**  
  Built with **Maven Wrapper** (`mvnw`) and the **javafx‑maven‑plugin** for one‑command runs and native image packaging.

---

## 🗂️ Project Structure
```
GameOfThrones/
├── pom.xml                     # Maven configuration & JavaFX plugin
├── mvnw / mvnw.cmd             # Maven wrapper scripts
├── src/
│   ├── main/java/
│   │   └── com/example/gameofthrones/
│   │       ├── GameMenu.java   # Animated menu overlay
│   │       ├── HelloApplication.java  # Boots the maze scene
│   │       ├── Maze.java       # Core maze logic & movement
│   │       ├── MakePath.java   # Parses text files into paths
│   │       └── …               # Other helper classes
│   └── main/resources/
│       └── com/example/gameofthrones/
│           ├── maze.fxml       # Scene graph for the maze
│           ├── hello-view.fxml # Sample FXML screen
│           ├── path1.txt       # Default maze grid (6×6)
│           └── images & audio
└── .mvn/wrapper/               # Maven wrapper JAR & props
```

---

## 🎮 Controls
| Key | Action |
|-----|--------|
| **U** | Move up |
| **D** | Move down |
| **L** | Move left |
| **R** | Move right |
| **Esc** | Toggle game menu |

---

## 🛠️ Requirements
- **JDK 17** or later (Java FX 17 requires ≥ 17)
- **Git**

*(No system‑wide Maven needed — the wrapper handles it.)*

---

## 📦 Build & Run

```bash
# 1. Clone the repo
git clone https://github.com/ShohanNur/GameOfThrones.git
cd GameOfThrones

# 2. Run the game (downloads JavaFX deps automatically)
./mvnw clean javafx:run     # on Linux/macOS
mvnw.cmd clean javafx:run   # on Windows
```

> The first run will download Maven & JavaFX dependencies to your local cache.

### Creating a Native Image (optional)

```bash
./mvnw javafx:jlink   # produces target/app/
```

Distribute the `app` folder for a self‑contained runtime.

---

## 📝 Customising Mazes
1. Create a new file in `src/main/resources/com/example/gameofthrones/` named `path2.txt`.  
2. Add a 6‑line grid of `0`s (walkable) and `1`s (wall), e.g.:

```
111111
100001
101101
101001
100001
111111
```

3. Adjust the `random` variable in `Maze.init()` or implement a loader to iterate multiple levels.

---

## 💡 Troubleshooting
- **Black window or missing images**  
  Ensure all images/sounds are inside the same `resources` package.  
- **Audio doesn’t play**  
  Confirm the MP3 path is on the classpath; replace hard‑coded absolute paths with resource URLs.

---

## 📄 License
This project is released under the **MIT License** — feel free to fork, hack, and enjoy.

---

*Winter might be coming, but your Java FX skills will be fire!* 🔥
