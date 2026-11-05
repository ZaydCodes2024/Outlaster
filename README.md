# Outlaster

**Theme - Small But Fun**

Outlaster - https://zayd-game-dev.itch.io/outlaster

## Game Idea

* First-Person Shooter
* Enemies are like Homing Missiles
* Game Rounds
* Few Maps
* Weapon Upgrades
* Difficulty Scaling
* Single Player

## Description

Outlaster is a single-player, wave-based first-person shooter built in Unity. The player is placed in an arena and must survive against enemies that behave like homing missiles — always flying in your direction, and relentlessly chasing you down. The game is structured in rounds, with each round getting progressively harder through difficulty scaling.

Between rounds, the player can pick from randomly offered upgrade skills (damage, double damage, health, stamina, dash, etc.), allowing different builds across every run. How long can you outlast?

## Key Features

* **First-Person Shooter Gameplay** — Classic FPS controls with mouse look, movement, jumping, and shooting.
* **Homing Missile Enemies** — Enemies fly toward and home in on the player, exploding on contact.
* **Round-Based System** — The game is divided into rounds; clear all enemies to advance to the next round.
* **Difficulty Scaling** — Enemy count and stats (speed, health, damage) increase each round.
* **Upgrade Skills** — Choose from a variety of upgrade skills (ScriptableObjects) after each round:
  * Damage Skill
  * Health Skill
  * Stamina Skill
* **UI & Feedback**
  * Crosshair, hit reticle, and damage indicators
  * Player HUD (health, stamina, etc.)
  * Pause menu, options, game over screen
  * Main menu and loading screen
* **Audio Feedback** — Weapon shooting/landing, footsteps, jumps, enemy growls/hurts/death, player hurt, game over, and round number whoosh SFX, with a synthwave music track.

## Screenshots

### Homing Missile Enemies

![Homing Missile Enemies](Enemies.jpg)

### Round System & Difficulty Scaling

![Round System](RoundSystem.jpg)

### Upgrade Skills

| Damage, Stamina & Health Skills |
|:---:|
| ![Upgrade Skills](Skills.jpg) |

### Player HUD & Combat Feedback

| Player HUD | Crosshair & Hit Reticle | Damage Indicators |
|---|---|---|
| ![Player HUD](PlayerHUD.jpg) | ![Crosshair & Hit Reticle](HitReticle.jpg) | ![Damage Indicators](DamageIndicator.jpg) |

### Menus

| Main Menu | Pause Menu | Options | Game Over |
|---|---|---|---|
| ![Main Menu](MainMenu.jpg) | ![Pause Menu](Paused.jpg) | ![Options](Options.jpg) | ![Game Over](GameOver.jpg) |

## Tech Stack

* **Engine:** Unity 6000.3.8f1
* **Render Pipeline:** Universal Render Pipeline (URP) with global volume profiles and a custom skybox
* **Input:** Unity Input System (`InputSystem_Actions.inputactions` with a generated C# wrapper)
* **Camera:** Cinemachine
* **UI:** Unity UI (uGUI) + TextMesh Pro
* **Other:** Timeline, Visual Scripting, Particle Systems

## Scenes

| Scene | Purpose |
|---|---|
| `LoadingScene.unity` | Initial loading scene (with loader callback) |
| `MainMenuScene.unity` | Main menu |
| `GameScene.unity` | Main gameplay scene |
| `GameOverScene.unity` | Game over screen |

## Folder Structure

```
Outlaster-main/
├── README.md
├── ProjectSettings/           # Unity project settings (physics, audio, input, URP, etc.)
├── Packages/                  # Unity package manifest (Cinemachine, URP, Input System, TMP, etc.)
├── Assets/
│   ├── Animations/
│   │   ├── Animators/             # Animator controllers
│   │   ├── Enemy Animations/      # Enemy animation clips
│   │   ├── Game UI/               # UI animation clips
│   │   ├── Player UI Animations/  # Player HUD animation clips
│   │   └── Weapon Animations/     # Weapon animation clips
│   ├── Art/
│   │   ├── Materials/             # Art materials
│   │   ├── Player UI/             # Crosshair, damage indicator, player UI PSDs
│   │   └── Skybox/                # Custom skybox
│   ├── Global Volume/             # URP global volume profile (GameScene post-processing)
│   ├── Input Action/              # Input System actions + generated C# class
│   ├── Layer Lab/                 # Third-party icon pack (PictoIcon pack) + panel scripts
│   ├── Materials/                 # Scene/weapon/enemy/particle materials
│   ├── Plugins/
│   │   └── Trinary Software/      # Editor timing/delay utilities
│   ├── Prefabs/                   # Enemy, bullet trail, enemy trail, death/hurt particles
│   ├── Resources/                 # Runtime-loaded assets
│   ├── Scenes/
│   │   ├── GameScene/             # Lighting data + player volume profile
│   │   ├── LoadingScene.unity
│   │   ├── MainMenuScene.unity
│   │   ├── GameScene.unity
│   │   └── GameOverScene.unity
│   ├── Script/
│   │   ├── Animation Scripts/     # AnimationSystem, PlayerHUDAnimations, PlayerWeaponAnimations
│   │   ├── Manager Scripts/       # GameManager, MusicManager, SoundManager, UpgradeSkillManager
│   │   ├── Player Scripts/        # Player, PlayerHealth, PlayerLook, PlayerMovement,
│   │   │                          # PlayerSounds, PlayerStamina, PlayerStats
│   │   ├── SO/                    # ScriptableObject classes (AudioClipSO, UpgradeSkillSO,
│   │   │                          # UpgradeSkillListSO)
│   │   ├── UI Scripts/            # MainMenuUI, PlayerUI, CrosshairUI, HitReticleUI,
│   │   │                          # DamageIndicatorUI, GameOverUI, GamePauseUI, OptionsUI,
│   │   │                          # UpgradeSkillUI, UpgradeSkillSingleUI
│   │   ├── CameraShake.cs
│   │   ├── Crosshair.cs
│   │   ├── DestroyOnTime.cs
│   │   ├── Enemy.cs / EnemySounds.cs / EnemyStats.cs
│   │   ├── GameInput.cs
│   │   ├── GameUISounds.cs
│   │   ├── IHealth.cs / StatType.cs
│   │   ├── InteractionController.cs
│   │   ├── Loader.cs / LoaderCallback.cs / ResetStaticData.cs
│   │   ├── PlayGameOver.cs
│   │   ├── UpgradeEffect.cs / UpgradeTarget.cs
│   │   └── Weapon.cs / WeaponController.cs
│   ├── ScriptableObjects/
│   │   ├── Upgrade Skill SO/      # Damage, Double Damage, Health, Stamina, Dash skill assets
│   │   └── UpgradeSkillListSO/    # Upgrade skill list asset
│   ├── Sounds/
│   │   ├── Music/                 # Background music track
│   │   └── SFX/                   # Footsteps, jumps, gunshot, enemy/player hurt,
│   │                              # enemy death, game over, round whoosh, etc.
│   ├── _Recovery/                 # Unity editor recovery files
│   ├── TextMesh Pro/              # TMP essentials (fonts, shaders, sprites)
│   └── URP/                       # URP renderer/pipeline settings
├── Logs/                      # Unity import/shader compiler logs
├── UserSettings/              # User-specific editor preferences
├── Library/                   # (Generated) Unity asset/shader caches — do not edit
└── Temp/                      # (Generated) Temporary build data — do not edit
```

## Core Scripts Overview

| Script | Responsibility |
|---|---|
| `GameManager.cs` | Round flow, difficulty scaling, upgrade skill offering |
| `UpgradeSkillManager.cs` | Handles upgrade skill application between rounds |
| `Enemy.cs` / `EnemyStats.cs` | Enemy behavior (homing movement, combat) and per-round stats |
| `Player.cs` / `PlayerMovement.cs` / `PlayerLook.cs` | Player controller, movement, and mouse look |
| `PlayerHealth.cs` / `PlayerStamina.cs` / `PlayerStats.cs` | Player health, stamina, and stats |
| `Weapon.cs` / `WeaponController.cs` | Weapon behavior and shooting |
| `Crosshair.cs` / `HitReticleUI.cs` / `DamageIndicatorUI.cs` | Aiming feedback |
| `SoundManager.cs` / `MusicManager.cs` / `AudioClipSO.cs` | Centralized audio playback |
| `UpgradeSkillSO.cs` / `UpgradeSkillListSO.cs` | Upgrade skill ScriptableObjects and upgrade pool |
| `Loader.cs` / `LoaderCallback.cs` | Scene loading between main menu and game |

## Getting Started

1. Install **Unity 6000.3.8f1** (tested version, via [Unity Hub](https://unity.com/download)).
2. Clone or download this repository.
3. Open the project folder in Unity Hub and open it with the matching editor version.
4. Let Unity import assets, then open `Assets/Scenes/LoadingScene.unity` (or `MainMenuScene.unity`) and press **Play**.
5. To build, use **File > Build Settings**, add the scenes (`LoadingScene`, `MainMenuScene`, `GameScene`, `GameOverScene`), and build for your target platform.

## Music

* Music by <a href="https://pixabay.com/users/elephantgreen-42056970/?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=221328">Dmytro Kuvalin</a> from <a href="https://pixabay.com/music//?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=221328">Pixabay</a>

## SFX

* Sound Effect by <a href="https://pixabay.com/users/soundreality-31074404/?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=384629">Jurij</a> from <a href="https://pixabay.com/sound-effects//?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=384629">Pixabay</a>

* Sound Effect by <a href="https://pixabay.com/users/dragon-studio-38165424/?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=376875">DRAGON-STUDIO</a> from <a href="https://pixabay.com//?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=376875">Pixabay</a>

* Sound Effect by <a href="https://pixabay.com/users/mollyroselee-9214707/?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=513256">Mollyroselee</a> from <a href="https://pixabay.com/sound-effects//?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=513256">Pixabay</a>

* Sound Effect by <a href="https://pixabay.com/users/phatphrogstudio-54178146/?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=496706">PhatPhrogStudio</a> from <a href="https://pixabay.com//?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=496706">Pixabay</a>

* Sound Effect by <a href="https://pixabay.com/users/u_68csiaifb5-52462238/?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=442718">u_68csiaifb5</a> from <a href="https://pixabay.com//?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=442718">Pixabay</a>

* Sound Effect by <a href="https://pixabay.com/users/ragecore29-54507225/?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=478992">Randy Jr</a> from <a href="https://pixabay.com//?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=478992">Pixabay</a>

* Sound Effect by <a href="https://pixabay.com/users/universfield-28281460/?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=352462">Universfield</a> from <a href="https://pixabay.com//?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=352462">Pixabay</a>

* Sound Effect by <a href="https://pixabay.com/users/freesound_community-46691455/?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=29401">freesound_community</a> from <a href="https://pixabay.com//?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=29401">Pixabay</a>

* Sound Effect by <a href="https://pixabay.com/users/dennish18-26151496/?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=146189">Dennis</a> from <a href="https://pixabay.com//?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=146189">Pixabay</a>
