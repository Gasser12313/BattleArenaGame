```markdown
# 🎮 Battle Arena

<div align="center">

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![JavaFX](https://img.shields.io/badge/JavaFX-ED8B00?style=for-the-badge&logo=java&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)

**A 2D Local Multiplayer Fighting Game**

</div>

## ✨ Features

### 🎭 Four Unique Characters
- **Warrior** - Balanced tank with high defense
- **Mage** - Area damage specialist with magic attacks
- **Archer** - Ranged attacker with high mobility
- **Assassin** - High-speed melee damage dealer

### 🔫 Six Different Weapons
- **Pistol** - Balanced rapid fire
- **Shotgun** - High damage spread shots
- **Sniper Rifle** - Long-range precision
- **Flame Thrower** - Continuous fire damage
- **Laser Rifle** - Energy beam attacks
- **Recurve Bow** - Traditional archery

### 🎨 Visual Excellence
- Particle effects and explosions
- Screen shake on heavy hits
- Dynamic health bars with animations
- Smooth character animations
- Glowing visual effects

### 🔊 Immersive Audio
- Background music with volume control
- Sound effects for all actions
- Victory and defeat fanfares
- Menu navigation sounds

## 🚀 Quick Start

### Method 1: Using IDE (Recommended)
```bash
git clone https://github.com/yourusername/BattleArena.git
cd BattleArena
```
1. Open in IntelliJ/Eclipse
2. Set VM Options: `--module-path "path/to/javafx-sdk/lib" --add-modules javafx.controls,javafx.media`
3. Run `application.Main`

### Method 2: Command Line (Maven)
```bash
# Clone and compile
git clone https://github.com/yourusername/BattleArena.git
cd BattleArena
mvn clean compile

# Run game (update JavaFX path)
java --module-path "/path/to/javafx-sdk/lib" \
     --add-modules javafx.controls,javafx.media \
     -cp "target/classes:src/main/resources" \
     application.Main
```

### Method 3: Using Scripts
```bash
# Windows
run.bat

# Linux/Mac
chmod +x run.sh
./run.sh
```

## 🎮 Controls

### Player 1 (Blue)
| Action | Key |
|--------|-----|
| Move Up | W |
| Move Down | S |
| Move Left | A |
| Move Right | D |
| Shoot | F |
| Switch Weapon | Q |
| Reload | 1 |

### Player 2 (Red)
| Action | Key |
|--------|-----|
| Move Up | ↑ |
| Move Down | ↓ |
| Move Left | ← |
| Move Right | → |
| Shoot | L |
| Switch Weapon | P |
| Reload | 0 |

### Game Controls
| Action | Key |
|--------|-----|
| Pause/Resume | ESC |
| Music Toggle | Pause Menu |
| Sound Toggle | Pause Menu |

## 📊 Character Stats

| Character | Health | Speed | Defense | Damage Type | Default Weapon |
|-----------|--------|-------|---------|-------------|----------------|
| Warrior | 150 | Medium | High | Balanced | Pistol |
| Mage | 100 | Low | Low | Area | Flame Thrower |
| Archer | 120 | High | Medium | Ranged | Recurve Bow |
| Assassin | 90 | Very High | Low | High | Shotgun |

## 🔫 Weapon Stats

| Weapon | Damage | Speed | Cooldown | Ammo |
|--------|--------|-------|----------|------|
| Pistol | 15 | 8 | 400ms | 12 |
| Shotgun | 60 | 6 | 800ms | 6 |
| Sniper Rifle | 40 | 15 | 1200ms | 4 |
| Flame Thrower | 5 | 4 | 100ms | 50 |
| Laser Rifle | 25 | 12 | 300ms | 20 |
| Recurve Bow | 28 | 10 | 600ms | 15 |

## 📁 Complete Project Structure

```
BattleArena/
│
├── src/main/java/
│   ├── application/
│   │   ├── Main.java
│   │   ├── SceneManager.java
│   │   ├── CharacterSelectionScene.java
│   │   ├── GameScene.java
│   │   └── GameOverScene.java
│   │
│   ├── animations/
│   │   ├── AnimationManager.java
│   │   ├── GameAnimations.java
│   │   ├── ParticleEffects.java
│   │   ├── ParticleSystem.java
│   │   ├── SpriteAnimation.java
│   │   └── TransitionEffects.java
│   │
│   ├── audio/
│   │   ├── AudioManager.java
│   │   ├── BackgroundMusic.java
│   │   └── SoundEffect.java
│   │
│   ├── characters/
│   │   ├── Fighter.java
│   │   ├── Warrior.java
│   │   ├── Mage.java
│   │   ├── Archer.java
│   │   ├── Assassin.java
│   │   └── CharacterFactory.java
│   │
│   ├── config/
│   │   ├── CharacterConfig.java
│   │   ├── GameConfig.java
│   │   └── WeaponConfig.java
│   │
│   ├── input/
│   │   ├── ControlScheme.java
│   │   └── InputManager.java
│   │
│   ├── physics/
│   │   ├── Vector2D.java
│   │   ├── PhysicsEngine.java
│   │   └── CollisionDetector.java
│   │
│   ├── projectiles/
│   │   ├── Projectile.java
│   │   ├── ProjectileManager.java
│   │   ├── Bullet.java
│   │   ├── Arrow.java
│   │   ├── Fireball.java
│   │   ├── LaserBeam.java
│   │   ├── ShotgunPellet.java
│   │   └── SniperBullet.java
│   │
│   ├── ui/
│   │   ├── AbilityButton.java
│   │   ├── CooldownIndicator.java
│   │   ├── HealthBar.java
│   │   ├── PauseMenuUI.java
│   │   ├── ScoreDisplay.java
│   │   ├── TimerDisplay.java
│   │   └── WeaponHUD.java
│   │
│   └── weapons/
│       ├── Weapon.java
│       ├── WeaponManager.java
│       ├── Pistol.java
│       ├── Shotgun.java
│       ├── SniperRifle.java
│       ├── FlameThrower.java
│       ├── LaserRifle.java
│       └── RecurveBow.java
│
├── src/main/resources/
│   ├── sounds/
│   │   ├── background_music.mp3
│   │   ├── shoot.wav
│   │   ├── hit.wav
│   │   ├── explosion.wav
│   │   ├── weapon_switch.wav
│   │   ├── ability.wav
│   │   ├── victory.wav
│   │   ├── defeat.wav
│   │   ├── menu_select.wav
│   │   └── menu_confirm.wav
│   │
│   └── icon/
│       ├── warrior.jpg
│       ├── mage.jpg
│       ├── archer.jpg
│       └── assassin.jpg
│
├── lib/                      # JavaFX libraries (optional)
│   ├── javafx.base.jar
│   ├── javafx.controls.jar
│   ├── javafx.graphics.jar
│   └── javafx.media.jar
│
├── target/                   # Maven build output (auto-generated)
│   ├── classes/
│   ├── generated-sources/
│   └── BattleArena.jar
│
├── .gitignore
├── README.md
├── LICENSE
├── pom.xml                  # Maven configuration
├── build.gradle             # Gradle configuration (alternative)
├── module-info.java        # Java module system (Java 9+)
├── run.bat                 # Windows launcher script
├── run.sh                  # Linux/Mac launcher script
└── quickstart.sh           # One-click setup script
```

## 📊 File Count Breakdown

| Category | File Count | Description |
|----------|------------|-------------|
| **Java Classes** | ~45-50 files | Core game logic and systems |
| **Configuration** | 5-7 files | Build and project config |
| **Resources** | 14 files | Sounds and images |
| **Scripts** | 3-4 files | Launchers and helpers |
| **Total** | ~65-70 files | Complete project |

## 🗂️ Package Details

### **application/** - Game Flow Control
- `Main.java` - Application entry point
- `SceneManager.java` - Scene transitions
- `CharacterSelectionScene.java` - Character selection UI
- `GameScene.java` - Main gameplay logic
- `GameOverScene.java` - Victory/defeat screens

### **animations/** - Visual Effects
- Particle systems, screen shakes, transitions
- Sprite animations and special effects

### **audio/** - Sound System
- Background music management
- Sound effect playback
- Volume controls

### **characters/** - Playable Characters
- Base Fighter class
- 4 unique character types
- Character factory pattern

### **config/** - Game Settings
- Character statistics
- Weapon properties
- Game constants

### **physics/** - Game Physics
- Vector mathematics
- Collision detection
- Movement physics

### **projectiles/** - Attack System
- Different projectile types
- Projectile management
- Damage calculation

### **ui/** - User Interface
- Health bars and weapon HUD
- Pause menu system
- Score displays and timers

### **weapons/** - Combat System
- Weapon base class
- 6 unique weapon types
- Weapon switching and management

## 📦 Build Configuration

### **For Maven Users** (`pom.xml`)
- Java 11+ compatibility
- JavaFX dependencies
- Build plugins for packaging
- Test configuration

### **For Gradle Users** (`build.gradle`)
- JavaFX plugin setup
- Dependency management
- Application packaging
- Test framework

## 🎵 Adding Assets

### Sound Files (place in `src/main/resources/sounds/`)
- `background_music.mp3` - Game background music
- `shoot.wav` - Shooting sound
- `hit.wav` - Hit impact sound
- `explosion.wav` - Explosion sound
- `weapon_switch.wav` - Weapon switching sound
- `ability.wav` - Ability activation sound
- `victory.wav` - Victory fanfare
- `defeat.wav` - Defeat sound
- `menu_select.wav` - Menu navigation
- `menu_confirm.wav` - Menu confirmation

### Character Icons (place in `src/main/resources/icon/`)
- `warrior.jpg` - Warrior character icon (100x100px recommended)
- `mage.jpg` - Mage character icon
- `archer.jpg` - Archer character icon
- `assassin.jpg` - Assassin character icon

## 🐛 Troubleshooting

| Issue | Solution |
|-------|----------|
| "JavaFX runtime components missing" | Add JavaFX SDK to module path |
| "No sound playing" | Check sound files in resources/sounds/ |
| "Controls not working" | Ensure window has focus |
| "Game runs slowly" | Close other applications |
| "Icons not showing" | Check icon files in resources/icon/ |
| "Class not found" | Rebuild project with Maven/Gradle |


---

<div align="center">
**Made with ❤️ and Java**
</div>
```
