# Battle Arena - JavaFX 2D Fighter Game 🎮

<div align="center">

![Battle Arena Banner](docs/banner.png)

[![Java 17+](https://img.shields.io/badge/Java-17%2B-orange?logo=openjdk&style=for-the-badge)](https://openjdk.org/)
[![JavaFX](https://img.shields.io/badge/JavaFX-17%2B-blue?logo=javafx&style=for-the-badge)](https://openjdk.org/projects/javafx/)
[![MIT License](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge)]()
[![Multiplayer](https://img.shields.io/badge/Multiplayer-Local-blueviolet?style=for-the-badge)]()

**An immersive 2D fighting game with stunning visuals, dynamic combat, and multiple character classes**

</div>

## 📋 Table of Contents
- [🎮 Quick Start](#-quick-start)
- [🏗️ Project Architecture](#️-project-architecture)
- [👥 Character Classes](#-character-classes)
- [🔫 Weapons System](#-weapons-system)
- [⚔️ Combat Mechanics](#️-combat-mechanics)
- [📁 Complete Project Structure](#-complete-project-structure)
- [✨ Visual Effects](#-visual-effects)
- [🔧 Configuration](#-configuration)
- [🎯 Controls](#-controls)
- [🚀 Installation](#-installation)
- [📄 License](#-license)

---

## 🎮 Quick Start

```bash
# Clone and run with JavaFX 17+
git clone https://github.com/yourusername/battle-arena.git
cd battle-arena

# Set JavaFX path and run
java --module-path "path/to/javafx-sdk/lib" \
     --add-modules javafx.controls,javafx.fxml,javafx.media \
     -cp "out" application.Main
```

---

## 🏗️ Project Architecture

### 📊 System Overview
```
┌─────────────────────────────────────────────────────────────┐
│                    BATTLE ARENA ARCHITECTURE                 │
├─────────────────────────────────────────────────────────────┤
│  APPLICATION LAYER                                          │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐        │
│  │    Main     │  │ SceneManager│  │ GameScenes  │        │
│  │  (Entry)    │  │ (Navigation)│  │ (UI Screens)│        │
│  └─────────────┘  └─────────────┘  └─────────────┘        │
├─────────────────────────────────────────────────────────────┤
│  GAME LOGIC LAYER                                           │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐        │
│  │  Characters │  │   Weapons   │  │   Physics   │        │
│  │   (4 Types) │  │   (6 Types) │  │  (Collision)│        │
│  └─────────────┘  └─────────────┘  └─────────────┘        │
├─────────────────────────────────────────────────────────────┤
│  RENDERING LAYER                                            │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐        │
│  │ Animations  │  │ Particle FX │  │   UI/UX     │        │
│  │  (System)   │  │  (Manager)  │  │  (Components)│       │
│  └─────────────┘  └─────────────┘  └─────────────┘        │
├─────────────────────────────────────────────────────────────┤
│  SUPPORT LAYER                                              │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐        │
│  │    Audio    │  │    Input    │  │    Config   │        │
│  │  (Manager)  │  │  (Handler)  │  │   (Files)   │        │
│  └─────────────┘  └─────────────┘  └─────────────┘        │
└─────────────────────────────────────────────────────────────┘
```

---

## 👥 Character Classes

### 📊 Character Comparison Table

| Character | Health | Speed | Defense | Damage | Playstyle | Difficulty |
|-----------|--------|-------|---------|--------|-----------|------------|
| **Warrior** | 150 | ⭐⭐☆☆☆ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐☆☆ | Tank/Balanced | Easy |
| **Mage** | 100 | ⭐☆☆☆☆ | ⭐☆☆☆☆ | ⭐⭐⭐⭐☆ | Area Control | Medium |
| **Archer** | 120 | ⭐⭐⭐⭐☆ | ⭐⭐⭐☆☆ | ⭐⭐⭐☆☆ | Ranged/Kiting | Medium |
| **Assassin** | 90 | ⭐⭐⭐⭐⭐ | ⭐☆☆☆☆ | ⭐⭐⭐⭐⭐ | Burst/Speed | Hard |

### 🛡️ Warrior (Tank)
```java
public class Warrior extends Fighter {
    // Stats: High Health, Medium Speed, High Defense
    // Role: Frontline Tank
    // Strategy: Sustain damage while dealing consistent DPS
}
```

**Abilities:**
- ✅ **High Survivability**: 150 base HP (highest in game)
- ✅ **Balanced Damage**: Consistent damage output
- ✅ **Sturdy Defense**: Takes reduced damage from projectiles
- ⚠️ **Slow Movement**: Lowest mobility among characters

**Best With:** Pistol, Shotgun (close-range combat)

### 🔮 Mage (Area Control)
```java
public class Mage extends Fighter {
    // Stats: Low Health, Slow Speed, Area Damage
    // Role: Crowd Control Specialist
    // Strategy: Control space with fire attacks
}
```

**Abilities:**
- ✅ **Area Damage**: Attacks affect wider areas
- ✅ **Continuous Damage**: Flame Thrower excels with Mage
- ✅ **Visual Intimidation**: Large, intimidating particle effects
- ⚠️ **Fragile**: Lowest health pool (100 HP)
- ⚠️ **Slow**: Poor mobility

**Best With:** Flame Thrower, Laser Rifle (area denial)

### 🏹 Archer (Ranged Specialist)
```java
public class Archer extends Fighter {
    // Stats: Medium Health, High Speed, Ranged Focus
    // Role: Sniper/Kiter
    // Strategy: Maintain distance while attacking
}
```

**Abilities:**
- ✅ **High Mobility**: Fastest base movement speed
- ✅ **Ranged Advantage**: Projectiles have longer range
- ✅ **Evasion**: Small hitbox, hard to hit
- ⚠️ **Medium Damage**: Not the highest DPS
- ⚠️ **Positioning Dependent**: Requires spacing

**Best With:** Recurve Bow, Sniper Rifle (distance combat)

### 🗡️ Assassin (Burst Damage)
```java
public class Assassin extends Fighter {
    // Stats: Low Health, Extreme Speed, High Burst
    // Role: High-Risk High-Reward
    // Strategy: Quick strikes, in-and-out combat
}
```

**Abilities:**
- ✅ **Extreme Speed**: Fastest character in the game
- ✅ **Burst Damage**: Highest single-attack potential
- ✅ **Small Profile**: Hardest to hit due to size and speed
- ⚠️ **Fragile**: Very low health (90 HP)
- ⚠️ **High Skill Cap**: Requires precise timing

**Best With:** Shotgun, Pistol (close-range burst)

---

## 🔫 Weapons System

### 📊 Weapon Statistics Comparison

| Weapon | Damage | Speed | Cooldown | Ammo | Range | Type | Best For |
|--------|--------|-------|----------|------|-------|------|----------|
| **Pistol** | 15 | 8.0 | 400ms | 12 | Medium | Hitscan | All-round |
| **Shotgun** | 60 | 6.0 | 800ms | 6 | Short | Spread | Assassin |
| **Sniper** | 40 | 15.0 | 1200ms | 4 | Long | Precision | Archer |
| **Flame Thrower** | 5 | 4.0 | 100ms | 50 | Short | Area | Mage |
| **Laser Rifle** | 25 | 12.0 | 300ms | 20 | Medium | Beam | All-round |
| **Recurve Bow** | 28 | 10.0 | 600ms | 15 | Medium | Projectile | Archer |

### 🎯 Weapon Details

#### 🔫 **Pistol** - The All-Rounder
```java
public class Pistol extends Weapon {
    // Balanced stats for consistent performance
    // Default weapon for Warrior class
    // Projectile: Straight-line bullet
}
```
**Characteristics:**
- **Damage Type**: Single-target, direct hit
- **Strategy**: Reliable DPS, good for beginners
- **Visual**: Small bullet with tracer effect
- **Sound**: Sharp gunshot sound

#### 💥 **Shotgun** - Close-Range Dominator
```java
public class Shotgun extends Weapon {
    // Fires 8 pellets in a spread pattern
    // High damage up close, falls off with distance
    // Default weapon for Assassin class
}
```
**Characteristics:**
- **Damage Type**: Spread (8 pellets × 7.5 damage each)
- **Strategy**: Ambush tactics, corner fights
- **Visual**: Multiple particle effects
- **Sound**: Loud, impactful blast

#### 🎯 **Sniper Rifle** - Precision Tool
```java
public class SniperRifle extends Weapon {
    // High single-shot damage
    // Long cooldown for balance
    // Requires good aim and timing
}
```
**Characteristics:**
- **Damage Type**: Single-target, high precision
- **Strategy**: Pick off enemies from distance
- **Visual**: Fast-moving, glowing projectile
- **Sound**: Distinctive high-powered shot

#### 🔥 **Flame Thrower** - Area Denial
```java
public class FlameThrower extends Weapon {
    // Continuous stream of fire
    // Low per-hit, high DPS
    // Excellent for controlling space
}
```
**Characteristics:**
- **Damage Type**: Area-of-effect, continuous
- **Strategy**: Zone control, pressure application
- **Visual**: Fireball particles with trail
- **Sound**: Constant flame whooshing

#### ⚡ **Laser Rifle** - Rapid Fire
```java
public class LaserRifle extends Weapon {
    // Fast projectiles with piercing effect
    // Good for hitting moving targets
    // Balanced damage and fire rate
}
```
**Characteristics:**
- **Damage Type**: Beam, piercing
- **Strategy**: Tracking moving targets
- **Visual**: Laser beam with glow effect
- **Sound**: High-energy zap

#### 🏹 **Recurve Bow** - Skill Weapon
```java
public class RecurveBow extends Weapon {
    // Arcing projectile trajectory
    // Can shoot over obstacles
    // Requires leading shots
}
```
**Characteristics:**
- **Damage Type**: Projectile with arc
- **Strategy**: Indirect fire, prediction shots
- **Visual**: Arrow with physical rotation
- **Sound**: Bow release with arrow whoosh

---

## ⚔️ Combat Mechanics

### 🎯 Hit System
```java
// Collision Detection Logic
public class CollisionDetector {
    public static boolean checkProjectileHit(Projectile p, Fighter f) {
        // Character-specific hitbox adjustments
        // Warriors: 90% of visual size (easier to hit)
        // Assassins: 75% of visual size (harder to hit)
        // Dynamic collision based on character type
    }
}
```

### 💥 Damage Calculation
```java
// Example damage flow
public void handlePlayerHit(Fighter player, Projectile projectile) {
    double damage = projectile.getDamage();
    
    // Apply character-specific damage modifiers
    if (player instanceof Warrior) {
        damage *= 0.9; // Warriors take 10% less damage
    } else if (player instanceof Assassin) {
        damage *= 1.1; // Assassins take 10% more damage
    }
    
    player.takeDamage(damage);
}
```

### ⚡ Special Effects Per Character

<div class="character-effects">

#### 🛡️ **Warrior Effects**
- **Hit Flash**: Red flash on taking damage
- **Low Health Pulse**: Health bar pulses red below 30% HP
- **Death Effect**: Turns gray and fades slowly

#### 🔮 **Mage Effects**
- **Ability Glow**: Purple aura when using specials
- **Fire Trail**: Leaves temporary fire particles
- **Death Explosion**: Small magical explosion on death

#### 🏹 **Archer Effects**
- **Dodge Effect**: Speed lines when moving quickly
- **Critical Hit**: Golden flash on headshots
- **Death Animation**: Falls backwards with arrow rain

#### 🗡️ **Assassin Effects**
- **Speed Blur**: Motion blur at high speeds
- **Backstab Bonus**: Extra damage from behind
- **Death Vanish**: Disappears in smoke cloud

</div>

---

## 📁 Complete Project Structure

```
battle-arena/
├── 📂 src/main/java/
│   ├── 📂 application/                    # Main application entry points
│   │   ├── Main.java                     # Application launcher
│   │   ├── SceneManager.java             # Scene navigation controller
│   │   ├── CharacterSelectionScene.java  # Character selection UI
│   │   ├── GameScene.java               # Main gameplay logic
│   │   └── GameOverScene.java           # End game screen
│   │
│   ├── 📂 characters/                    # Character system
│   │   ├── Fighter.java                  # Base character class
│   │   ├── CharacterFactory.java         # Character creation factory
│   │   ├── Warrior.java                  # Tank character
│   │   ├── Mage.java                     # Magic character
│   │   ├── Archer.java                   # Ranged character
│   │   └── Assassin.java                 # Speed character
│   │
│   ├── 📂 weapons/                       # Weapon system
│   │   ├── Weapon.java                   # Base weapon class
│   │   ├── WeaponManager.java            # Weapon inventory system
│   │   ├── Pistol.java                   # Standard firearm
│   │   ├── Shotgun.java                  # Spread weapon
│   │   ├── SniperRifle.java              # Precision rifle
│   │   ├── FlameThrower.java             # Area weapon
│   │   ├── LaserRifle.java               # Energy weapon
│   │   └── RecurveBow.java               # Archery weapon
│   │
│   ├── 📂 projectiles/                   # Projectile system
│   │   ├── Projectile.java               # Base projectile
│   │   ├── Bullet.java                   # Pistol projectile
│   │   ├── ShotgunPellet.java            # Shotgun spread
│   │   ├── SniperBullet.java             # Sniper round
│   │   ├── Fireball.java                 # Flame thrower projectile
│   │   ├── LaserBeam.java                # Laser rifle beam
│   │   ├── Arrow.java                    # Bow arrow
│   │   └── ProjectileManager.java        # Active projectile tracker
│   │
│   ├── 📂 animations/                    # Visual effects system
│   │   ├── AnimationManager.java         # Central animation controller
│   │   ├── GameAnimations.java           # Game-specific animations
│   │   ├── ParticleEffects.java          # Particle system
│   │   ├── ParticleSystem.java           # Particle manager
│   │   ├── SpriteAnimation.java          # Sprite-based animations
│   │   └── TransitionEffects.java        # UI transitions
│   │
│   ├── 📂 physics/                       # Physics engine
│   │   ├── Vector2D.java                 # 2D vector mathematics
│   │   ├── CollisionDetector.java        # Collision detection
│   │   └── PhysicsEngine.java            # Physics simulation
│   │
│   ├── 📂 ui/                            # User interface components
│   │   ├── HealthBar.java                # Dynamic health display
│   │   ├── WeaponHUD.java                # Weapon information HUD
│   │   ├── PauseMenuUI.java              # Pause menu interface
│   │   ├── ScoreDisplay.java             # Score tracking
│   │   ├── TimerDisplay.java             # Game timer
│   │   ├── CooldownIndicator.java        # Ability cooldown UI
│   │   └── AbilityButton.java            # Special ability button
│   │
│   ├── 📂 audio/                         # Audio management
│   │   ├── AudioManager.java             # Sound effect controller
│   │   ├── BackgroundMusic.java          # Music player
│   │   └── SoundEffect.java              # Sound effect enum
│   │
│   ├── 📂 input/                         # Input handling
│   │   ├── InputManager.java             # Keyboard input processor
│   │   └── ControlScheme.java            # Control mapping
│   │
│   └── 📂 config/                        # Game configuration
│       ├── GameConfig.java               # Main game settings
│       ├── CharacterConfig.java          # Character stats
│       └── WeaponConfig.java             # Weapon stats
│
├── 📂 src/main/resources/               # Game assets
│   ├── 📂 sounds/                       # Audio files
│   │   ├── shoot.wav/mp3                # Weapon firing
│   │   ├── hit.wav/mp3                  # Hit impact
│   │   ├── explosion.wav/mp3            # Explosion effect
│   │   ├── weapon_switch.wav/mp3        # Weapon switch
│   │   ├── ability.wav/mp3              # Special ability
│   │   ├── victory.wav/mp3              # Victory fanfare
│   │   ├── defeat.wav/mp3               # Defeat sound
│   │   ├── menu_select.wav/mp3          # Menu navigation
│   │   ├── menu_confirm.wav/mp3         # Menu confirmation
│   │   └── background_music.mp3         # Background track
│   │
│   └── 📂 icon/                         # Character icons
│       ├── warrior.jpg                  # Warrior icon
│       ├── mage.jpg                     # Mage icon
│       ├── archer.jpg                   # Archer icon
│       └── assassin.jpg                 # Assassin icon
│
├── 📂 docs/                            # Documentation
│   ├── 📂 architecture/                # Architecture diagrams
│   ├── 📂 screenshots/                 # Game screenshots
│   └── 📂 api/                         # API documentation
│
├── 📂 lib/                            # External libraries
│   └── javafx-sdk-XX/                 # JavaFX SDK
│
├── LICENSE                           # MIT License
├── README.md                        # This documentation
└── .gitignore                       # Git ignore file
```

### 🔑 Key Files Description

| File | Purpose | Importance |
|------|---------|------------|
| **Main.java** | Application entry point | Critical |
| **Fighter.java** | Base character class | Core Gameplay |
| **Weapon.java** | Base weapon class | Core Gameplay |
| **AnimationManager.java** | Visual effects controller | Visual Polish |
| **CollisionDetector.java** | Hit detection system | Game Mechanics |
| **SceneManager.java** | Screen navigation | User Experience |
| **AudioManager.java** | Sound system | Audio Experience |
| **HealthBar.java** | Health display UI | User Interface |

---

## ✨ Visual Effects System

### 🎭 Animation Categories

```java
public class AnimationManager {
    // 1. COMBAT EFFECTS
    public void createExplosion(double x, double y, Color color) {
        // Particle explosion with shockwave
    }
    
    public void createHitEffect(double x, double y, Color color) {
        // Sparkle effect on hit
    }
    
    // 2. CHARACTER EFFECTS
    public void createHealEffect(double x, double y) {
        // Green particles for healing
    }
    
    public void createLevelUpEffect(double x, double y) {
        // Golden spiral particles
    }
    
    // 3. UI EFFECTS
    public void shakeScreen(Node target, double intensity) {
        // Screen shake for impacts
    }
    
    public void flashHit(Shape shape, Color flashColor) {
        // Character flash on hit
    }
}
```

### 💫 Particle System Features
- **Dynamic Particle Count**: Adjusts based on performance
- **Color Variation**: Randomized hues within color ranges
- **Physics-based Movement**: Particles follow velocity and gravity
- **Lifetime Management**: Auto-cleanup of expired particles
- **Layer System**: Particles rendered in correct order

---

## 🔧 Configuration

### ⚙️ Character Configuration (`config/CharacterConfig.java`)
```java
public class CharacterConfig {
    public static class Warrior {
        public static final int HEALTH = 150;
        public static final double SPEED = 4.0;
        public static final String DEFAULT_WEAPON = "Pistol";
    }
    
    public static class Mage {
        public static final int HEALTH = 100;
        public static final double SPEED = 3.5;
        public static final String DEFAULT_WEAPON = "FlameThrower";
    }
    // ... Archer and Assassin configurations
}
```

### 🔫 Weapon Configuration (`config/WeaponConfig.java`)
```java
public class WeaponConfig {
    public static class Pistol {
        public static final double DAMAGE = 15;
        public static final double SPEED = 8;
        public static final long COOLDOWN = 400;
        public static final int AMMO = 12;
    }
    
    public static class Shotgun {
        public static final double DAMAGE = 60; // Total for all pellets
        public static final double SPEED = 6;
        public static final long COOLDOWN = 800;
        public static final int AMMO = 6;
    }
    // ... Other weapon configurations
}
```

### 🎮 Game Configuration (`config/GameConfig.java`)
```java
public class GameConfig {
    public static final int WINDOW_WIDTH = 1200;
    public static final int WINDOW_HEIGHT = 800;
    public static final int ARENA_WIDTH = 1200;
    public static final int ARENA_HEIGHT = 600;
    public static final double PLAYER_SPEED = 5.0;
    public static final double PROJECTILE_SPEED_MULTIPLIER = 10.0;
    
    // Dynamic arena sizing (adjusts to screen)
    public static double CURRENT_ARENA_WIDTH = ARENA_WIDTH;
    public static double CURRENT_ARENA_HEIGHT = ARENA_HEIGHT;
}
```

---

## 🎯 Controls Reference Card

<div align="center">

### 🎮 **Player 1 (Blue Team)**
| Action | Key | Visual Feedback |
|--------|-----|-----------------|
| **Move** | `W A S D` | Character rotation & movement |
| **Shoot** | `F` | Muzzle flash + projectile |
| **Switch Weapon** | `Q` | HUD animation + sound |
| **Reload** | `1` | Ammo bar refill animation |

### 🔴 **Player 2 (Red Team)**
| Action | Key | Visual Feedback |
|--------|-----|-----------------|
| **Move** | `↑ ↓ ← →` | Character rotation & movement |
| **Shoot** | `L` | Muzzle flash + projectile |
| **Switch Weapon** | `P` | HUD animation + sound |
| **Reload** | `0` | Ammo bar refill animation |

### ⏸️ **Game Controls**
| Action | Control | Effect |
|--------|---------|--------|
| **Pause** | `ESC` or Click Pause Button | Shows pause menu |
| **Resume** | `ESC` or Resume Button | Returns to game |
| **Menu Navigation** | Mouse | Hover effects + sounds |
| **Exit** | Exit Button | Returns to desktop |

</div>

---

## 🚀 Installation & Setup

### 📋 Prerequisites Checklist
- [ ] **JDK 17+** installed and configured
- [ ] **JavaFX SDK 17+** downloaded
- [ ] **IDE** (IntelliJ IDEA recommended)
- [ ] **Sound files** in `resources/sounds/` folder
- [ ] **Icon images** in `resources/icon/` folder

### 🔧 Step-by-Step Setup

#### 1. **Clone and Import**
```bash
git clone https://github.com/yourusername/battle-arena.git
cd battle-arena
```

#### 2. **Configure JavaFX in IntelliJ IDEA**
1. Open Project in IntelliJ
2. `File → Project Structure → Libraries`
3. Add JavaFX SDK `lib` folder
4. Add VM Options:
   ```
   --module-path "path/to/javafx-sdk/lib" 
   --add-modules javafx.controls,javafx.fxml,javafx.media
   ```

#### 3. **Add Required Assets**
Create folder structure and add:
```
resources/
├── sounds/
│   ├── shoot.wav
│   ├── hit.wav
│   └── ... (all 10 sound files)
└── icon/
    ├── warrior.jpg
    ├── mage.jpg
    ├── archer.jpg
    └── assassin.jpg
```

#### 4. **Build and Run**
```java
// Run Main.java from application package
// Or use run configuration with VM options
```

### 🐛 Troubleshooting Common Issues

| Issue | Solution |
|-------|----------|
| **"JavaFX runtime components missing"** | Ensure JavaFX SDK is added to module path |
| **No sound effects** | Check sound files exist in `resources/sounds/` |
| **Controls not working** | Click game window to focus, check key mappings |
| **Poor performance** | Reduce particle effects in `AnimationManager` |
| **Window too small** | Adjust `WINDOW_WIDTH/HEIGHT` in `GameConfig.java` |

---

## 📄 License

```
MIT License

Copyright (c) 2025 ok24591

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

### 📝 Usage Terms
- ✅ **Free to use** for personal and commercial projects
- ✅ **Modify and distribute** as needed
- ✅ **Credit appreciated** but not required
- ✅ **No warranty** provided - use at your own risk
- ⚠️ **JavaFX dependency** has its own licensing terms

---

<div align="center">

## 🎉 Ready to Battle?

**Choose your fighter, master your weapons, and dominate the arena!**

[![Start Playing](https://img.shields.io/badge/START_PLAYING-NOW-success?style=for-the-badge&logo=game-controller)]()

*"The arena awaits. Will you emerge victorious?"*

</div>

---

### 🔗 Quick Links
- [📥 Download Latest Release](#)
- [🐛 Report Issues](#)
- [💡 Request Features](#)
- [📚 View Documentation](#)
- [👥 Community Discord](#)

### 📊 Project Status
| Component | Status | Version |
|-----------|--------|---------|
| **Core Gameplay** | ✅ Complete | 1.0.0 |
| **Character System** | ✅ Complete | 1.0.0 |
| **Weapon System** | ✅ Complete | 1.0.0 |
| **Visual Effects** | ✅ Complete | 1.0.0 |
| **Audio System** | ✅ Complete | 1.0.0 |
| **Multiplayer** | ✅ Complete | 1.0.0 |
| **Documentation** | ✅ Complete | 1.0.0 |

---

**Made with ❤️ using Java & JavaFX**
