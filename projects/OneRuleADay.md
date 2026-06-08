---
layout: project
type: project
image: img/OneDayRule.png
title: "One Rule A Day Game"
date: 2026
published: True
labels:
    - 2D mobile
    - Unity
    - C#
    - Android
summary: "One Rule A Day is a 2D mobile puzzle-platformer built with Unity and C# for Android. The core idea of the game is that the gameplay rule changes every day, forcing players to solve the level in a different way each time. Instead of only testing platforming skills, the game challenges players to understand and adapt to daily constraints such as “No Jumping,” “No Moving Left,” “No Stopping,” “Only One Jump,” and “Reverse Controls”."
---
# One Rule A Day

> Every day, the rule changes.

## Project Overview

One Rule A Day is designed around a simple but replayable idea: the player faces a different rule every day. Instead of only testing platforming mechanics, the game challenges the player to understand the daily constraint and adapt their movement strategy.

The project includes five rule-specific levels. A daily loader scene selects the level using the current day of the year, which allows all players to receive the same daily challenge. Each level is built around one core rule, and breaking the rule immediately triggers a failure state.

This project was developed as a team-based Unity mobile game project. It demonstrates gameplay scripting, modular Unity component design, mobile UI interaction, 2D physics, scene management, and event-driven rule logic.

## Key Features

- Daily rule-based gameplay rotation
- Five rule-specific 2D platformer levels
- Android mobile touch controls
- Keyboard input support for testing in Unity Editor
- Player movement, jumping, landing, facing direction, and respawn logic
- Event-driven rule violation system
- Win and fail triggers
- Pause, hint/rule, restart, win, and fail UI panels
- Background music and sound effects
- Walking dust, landing dust, and fail flash visual effects
- Android native share functionality for sharing completed challenges

## Gameplay Rules

| Rule | Description |
|---|---|
| No Jumping | The player fails if they jump. |
| No Moving Left | The player fails if they move left. |
| No Stopping | The player fails if they stop after movement begins. |
| Only One Jump | The player may jump once; any additional jump causes failure. |
| Reverse Controls | Left and right movement controls are reversed. |

Rules rotate through a five-day cycle using the current calendar day.

## Tech Stack

- **Engine:** Unity 6
- **Language:** C#
- **Platform:** Android
- **Systems Used:** Unity 2D Physics, Unity UI, TextMesh Pro, Scene Management, AudioSource, Particle Systems

## Technical Implementation

### Daily Level Loading

The project uses a `DailyLevelLoader` script to select the active level. The selected level is based on `DateTime.Now.DayOfYear % numberOfLevels`, creating a simple daily rotation system. A manual override option is also included for testing specific levels in the Unity Editor.

### Rule Management System

The `RuleManager` controls the active rule for each level. It connects to the player through events such as:

- `OnJump`
- `OnMoveLeft`
- `OnStop`
- `OnLand`

This event-driven structure separates the player movement code from the rule-checking logic. As a result, movement remains reusable while new rules can be added more easily in the future.

### Player Controller

The `PlayerController` handles:

- Horizontal movement
- Jumping
- Ground detection
- Touch input
- Keyboard input
- Reverse control mode
- Facing direction
- Respawn behavior
- Game-over input locking

The controller supports both Unity Editor testing and Android mobile gameplay.

### UI System

The UI system includes:

- Rule text display
- Rule/hint panel
- Pause panel
- Fail panel
- Win panel
- Restart buttons
- Mobile movement and jump buttons

The `HUDController` manages game states such as playing, failed, and won. When the player wins or fails, the game pauses and displays the appropriate panel.

### Audio and Visual Feedback

The project includes several feedback systems to improve the game feel:

- Background music loop
- Walking sound
- Jump sound
- Landing sound
- Win sound
- Fail sound
- Button click sound
- Walking dust particles
- Landing dust effect
- Fail screen flash

## Project Structure

```text
OneRuleADay/
├── Assets/
│   ├── Animations/              # Player animation controller and clips
│   ├── Audio/                   # Music, player sounds, and UI sound effects
│   ├── Prefabs/                 # Environment, player, UI, VFX, and SFX prefabs
│   ├── Scenes/                  # Main menu, daily loader, and rule-specific levels
│   ├── Scripts/
│   │   ├── Audio/               # Music and sound effect managers
│   │   ├── GameUtilis/          # Level triggers and moving platform logic
│   │   ├── Player/              # Player controller, animation, and audio scripts
│   │   ├── Rules/               # Daily level loader and rule manager
│   │   ├── UI/                  # HUD, pause, menu, touch controls, and sharing
│   │   └── VFX/                 # Visual effect manager
│   └── Sprites/                 # Background, buttons, doors, platforms, and player sprites
├── ProjectSettings/
└── Packages/
```

## Main Scripts

| Script | Purpose |
|---|---|
| `PlayerController.cs` | Handles movement, jumping, input, ground detection, reverse controls, and player events. |
| `RuleManager.cs` | Applies the active daily rule and detects rule violations through player events. |
| `DailyLevelLoader.cs` | Loads the daily level based on the current calendar day. |
| `HUDController.cs` | Manages rule display, win/fail panels, restart logic, and game state. |
| `TouchMoveButton.cs` | Handles mobile left/right movement buttons. |
| `TouchJumpButton.cs` | Handles mobile jump button input. |
| `LevelTrigger.cs` | Detects win and fail trigger zones. |
| `MovingPlatformController.cs` | Controls moving platforms using two target points. |
| `SFXManager.cs` | Plays walking, jumping, landing, fail, win, and button sounds. |
| `VFXManager.cs` | Plays dust effects and fail flash effects. |
| `ShareManager.cs` | Uses Android native share to share the daily challenge result. |

## How to Run

1. Open the project in **Unity 6**.
2. Open the `OneRuleADay` Unity project folder.
3. Load the `MainMenu` scene.
4. Press **Play** in the Unity Editor.
5. Click **Start** to enter the daily level loader.

## How to Build for Android

1. Open the project in Unity.
2. Go to **File > Build Profiles**.
3. Select **Android** as the target platform.
4. Switch platform if needed.
5. Make sure `MainMenu` is included as the first scene in the build settings.
6. Click **Build** to generate the APK.

## What I Learned

Through this project, I gained practical experience with:

- Unity 2D game development
- C# gameplay scripting
- Mobile touch input implementation
- Event-driven gameplay logic
- Scene loading and build configuration
- UI state management
- Audio and visual feedback systems
- Team-based game development workflow
- Designing a replayable game mechanic around simple rules

## Future Improvements

- Add more daily rules and levels
- Add a level selection/debug menu for testing
- Save player completion history
- Add daily streak tracking
- Add more polished character animations
- Add better onboarding/tutorial screens
- Add online leaderboard support
- Improve level variety with more obstacles and interactive objects

## License
This project uses the MIT License.
