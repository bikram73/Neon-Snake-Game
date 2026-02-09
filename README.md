# 🐍 Neon Snake Game

A modern, cyberpunk-themed Snake game built with **TypeScript**, **Vite**, and **HTML5 Canvas**. It features a responsive neon UI, multiple game modes, power-ups, particle effects, and full mobile support.

![Neon-Snake-Game-Image](images/Snake_Game.png)

<div align="center">
  <a href="https://neon-snake-game-gamma.vercel.app/" target="_blank">
    <img src="https://img.shields.io/badge/PLAY_NOW-NEON_SNAKE-d946ef?style=for-the-badge&logo=gamepad&logoColor=white" alt="Play Now">
  </a>
</div>

## 🎮 Features

- **Thirteen Game Modes**:
  - **Classic**: Traditional snake gameplay with wall wrapping.
  - **Arcade**: Dynamic obstacles spawn and disappear over time, increasing the challenge.
  - **Box**: Closed walls where hitting the boundary results in losing a life.
  - **Gate**: Partial walls with neon-lit segments. The middle sections are open for wrapping, while the corners are deadly.
  - **Mirror**: Controls are reversed (Left becomes Right, Up becomes Down).
  - **Time Attack**: Score as many points as possible in 60 seconds.
  - **Portal**: Teleport between fixed corner portals. Positions interchange every 30 seconds (swapping between Top-Left/Bottom-Right and Bottom-Left/Top-Right) with a 5-second red flash warning.
  - **Maze**: Navigate through pre-defined maze layouts that change every few levels (5 unique layouts).
  - **Darkness**: The entire grid is pitch black. Only the immediate area around the snake's head and food emits light.
  - **Hunter**: Red "Hunter" dots spawn and chase the snake. Avoid them or they'll end your game.
  - **Stroop**: A psychological challenge where you must eat food that matches the *meaning* of the text, not its color (e.g., eat red food when "RED" appears, even if the text is blue).
  - **Splitter**: Eating special food temporarily splits your snake into multiple independent segments for added complexity.
  - **Zen**: No death from walls or self-collision, and lives are disabled. The game ends when the snake fills the entire grid (400 tiles). Once fully grown, the snake can no longer eat food.

- **Power-up System**:
  - 🔴 **Red Food (Target)**: +10 Score, increases snake length, and contributes to level progression.
  - 🟡 **Yellow Food (Invincibility)**: Grants 10 seconds of invincibility. You can pass through walls, obstacles, and yourself without taking damage. Spawns with a 20% chance after eating red food.
  - 🟢 **Green Food (Extra Life)**: Grants +1 Life. Does not increase snake length. Rare spawn (5% chance, max 2 per level).
  - 🔵 **Blue Food (Slow Motion)**: Temporarily reduces game speed for 10 seconds and adds a subtle blue tint to the background. Spawns with a 15% chance after eating red food.
  - 🟣 **Purple Food (Magnet)**: Automatically attracts nearby food to the snake's head for 5 seconds. Spawns with a 15% chance after eating red food.
  - 🟠 **Orange Food (Shrink)**: Reduces the snake's length by 3 segments (minimum length of 5). Spawns with a 10% chance after eating red food.
  - 🛡️ **Shield**: Provides protection from one collision. Lasts for 1 minute or until consumed. Spawns with a 10% chance after eating red food.

- **Progression**:
  - Level up every 50 points.
  - Game speed increases with every level.
  - In Arcade mode, the number of obstacles increases with the level.

- **Achievement Milestones**:
  - **Bronze Status**: Reaching 25 tiles turns the snake brown/bronze.
  - **Silver Status**: Reaching 50 tiles turns the snake silver.
  - **Golden Snake**: Reaching 75 tiles turns the snake into a glowing golden legend.
  - Each milestone triggers a special on-screen pop-up notification.

- **Visuals & Audio**:
  - **3D Snake Rendering**: Modern 3D spherical snake segments with realistic shading, eyes, and animated tongue.
  - **Respawn Protection**: After losing a life, the snake blinks and becomes invincible for 3 seconds.
  - **Screen Shake Effects**: Subtle camera shake when eating food or taking damage for enhanced feedback.
  - **Neon glow effects** for the snake and items with cyberpunk aesthetics.
  - **Particle explosion effects** upon death or taking damage.
  - **Dynamic Lighting**: In Darkness mode, realistic light radius around the snake's head and food items.
  - **Synthesized sound effects and background music** using the Web Audio API (no external assets required).
  - **Immersive UI**: Full-screen Main Menu, Mode Selection, and Statistics pages with a pulsing "START GAME" button.

- **Statistics & Achievements**:
  - **Persistent Tracking**: Tracks High Scores, Average Scores, and Low Scores for all 13 game modes.
  - **Medal System**: Displays earned Bronze, Silver, and Gold medals in a dedicated Statistics table.
  - **Share Stats**: One-click button to copy a formatted summary of your high scores and achievements to the clipboard.
  - **Global Navigation**: A persistent menu button (top-left) provides instant access to stats and settings.

- **Customization & Shop System**:
  - **Skin Shop**: Unlock and equip different snake skins using food counters earned during gameplay.
  - **Snake Model Shop**: Choose from various 3D snake models including spheres with eyes, mechanical designs, and special effects.
  - **Unlockable Content**: Skins and models are unlocked by eating specific food types, reaching score milestones, or achieving level goals in different game modes.
  - **Preview System**: Real-time preview of skins and snake models before purchasing or equipping.

- **Cross-Platform Controls**:
  - **Keyboard support** for desktop (Arrow Keys, WASD, Space/P for pause).
  - **Touch swipe** and **on-screen D-pad** for mobile.
  - **Haptic Feedback**: Subtle vibration on mobile control interactions.
  - **Responsive Design**: Optimized layouts for Desktop, Tablet, and Mobile views, including an improved pause menu.
  - **Adjustable UI Scale**: Customizable interface scaling for better accessibility.

- **Persistence**: 
  - **Game Data**: Detailed statistics (High/Low/Avg) and achievement medals are saved per mode for all 13 game modes.
  - **Preferences**: User settings (Sound, Music, Vibration, Level Up, Rainbow Skin) are automatically saved to local storage.
  - **Customization Data**: Unlocked skins, snake models, and food counters persist across sessions.
  - **Progress Tracking**: Individual progress tracking for each game mode's unlock requirements.

## 🕹️ Controls

### Desktop
- **Arrow Keys** or **WASD**: Move Snake (Up, Down, Left, Right)
- **Space / P**: Pause / Resume Game

### Mobile
- **Swipe**: Swipe anywhere on the canvas to change direction.
- **On-Screen D-Pad**: Tap the directional buttons below the game area.

## 🎨 Customization

### Visual Themes
You can easily customize the game's neon aesthetic by modifying the `COLORS` constant at the top of `src/main.ts`. This allows you to change the theme without digging through the rendering logic:

- **Background**: `COLORS.BACKGROUND` (default: `#1e293b`)
- **Snake**: `COLORS.SNAKE_HEAD` (`#ffffff`) and `COLORS.SNAKE_BODY` (`#d946ef`).
- **Items**: `COLORS.FOOD` (`#ff0055`), `COLORS.POWERUP` (`#facc15`), and `COLORS.LIFE` (`#00ff00`).
- **Obstacles**: `COLORS.OBSTACLE` (`#475569`).

### Unlockable Content
The game features an extensive customization system:

- **Skin Shop**: Unlock new snake colors and patterns by consuming specific food types during gameplay
- **Snake Model Shop**: Unlock 3D snake models with unique visual effects and animations
- **Progress-Based Unlocks**: Content unlocked through score achievements, level progression, and game mode mastery
- **Real-Time Preview**: Test skins and models before equipping them with the built-in preview system

## 📱 Mobile App Support

This game includes **Capacitor** integration for native mobile app deployment:

- **Android Support**: Full Android app build configuration included
- **Native Features**: Haptic feedback, responsive touch controls, and mobile-optimized UI
- **Cross-Platform**: Same codebase runs on web browsers and as native mobile apps

### Building for Mobile
```bash
# Build and sync to mobile platforms
npm run sync

# For Android development
cd android
./gradlew assembleDebug
```

## 📂 Project Structure

```text
snake_game/
├── index.html              # Main entry point and UI structure
├── package.json            # Project dependencies and build scripts
├── capacitor.config.ts     # Capacitor mobile app configuration
├── tsconfig.json           # TypeScript configuration
├── vite.config.ts          # Vite build tool configuration
├── android/                # Android app build files and configuration
├── src/
│   ├── main.ts             # Core game logic, state management, and rendering
│   └── style.css           # Cyberpunk theme, animations, and responsive layout
├── images/                 # Game screenshots and assets
├── LICENSE                 # Project license
└── README.md               # Project documentation
```

## 🛠️ Technical Implementation

### Core Logic (`main.ts`)
- **Game Loop**: Managed via `setInterval`, with the interval duration decreasing as the player levels up to increase difficulty.
- **State Management**: The `SnakeGame` class encapsulates all game states, including the snake's coordinates, active power-ups, current score, lives, and customization options.
- **Collision Detection**: Every frame, the engine checks the head's position against food, power-ups, obstacles, hunters, portals, and the snake's own body.
- **Coordinate System**: Uses a 20x20 grid system. Movement is calculated by adding/subtracting from X and Y coordinates before multiplying by the tile size for rendering.
- **Multi-Mode Logic**: Sophisticated game mode system with unique mechanics for each of the 13 available modes.

### Rendering
- **HTML5 Canvas**: High-performance 2D rendering with 3D visual effects.
- **3D Snake Effects**: Advanced rendering system that transforms 2D coordinates into 3D-looking spheres with realistic shading and lighting.
- **Neon Effects**: Achieved using `shadowBlur` and `shadowColor` properties on the Canvas context to create the glowing cyberpunk aesthetic.
- **Particles**: A comprehensive particle system handles explosion effects, power-up indicators, and visual feedback.
- **Dynamic Lighting**: Real-time lighting calculations for Darkness mode and special effects.

### Input & Audio
- **Input Handling**: Supports `keydown` events for desktop (Arrow Keys + WASD) and `touchstart`/`touchmove` for mobile swipe detection and D-pad interaction.
- **Web Audio API**: Generates sound effects and background music in real-time using oscillators (`sawtooth`, `sine`, `square`). No external audio files are required, keeping the bundle size extremely small.
- **Haptic Feedback**: Integrated vibration support for mobile devices with customizable intensity.

### Persistence & Customization
- **LocalStorage**: Automatically saves and retrieves high scores for all 13 game modes, user preferences, unlocked content, and progress tracking.
- **Skin System**: Advanced unlocking system based on food consumption, score milestones, and level achievements.
- **3D Models**: Multiple snake rendering styles with real-time preview capabilities.

## � Getting Started

### Prerequisites
- **Node.js** (v14 or higher) installed on your machine.

### Installation

1. Navigate to the project folder:
   ```bash
   cd snake_game
   ```
2. Install dependencies:
   ```bash
   npm install
   ```

### Running the Game

Start the development server:
```bash
npm run dev
```
Open your browser and navigate to the URL shown in the terminal (usually `http://localhost:5173`).

### Building for Production

To create a production build (e.g., for Vercel deployment):
```bash
npm run build
```

## 🛠️ Technologies Used

- **Vite**: Fast frontend tooling and development server.
- **TypeScript**: Type-safe game logic and state management.
- **HTML5 Canvas**: High-performance 2D rendering with 3D visual effects.
- **CSS3**: Responsive layout, neon styling, and mobile-first design.
- **Web Audio API**: Real-time sound synthesis and dynamic music.
- **Capacitor**: Cross-platform mobile app development framework.
- **LocalStorage API**: Persistent data storage for progress and preferences.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.
