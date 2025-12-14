# 🎮 Battle Arena

<div align="center">

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![JavaFX](https://img.shields.io/badge/JavaFX-ED8B00?style=for-the-badge&logo=java&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)

A **2D local multiplayer fighting game** with stunning visuals, smooth gameplay, and intense battles!

</div>

## ✨ Features

### 🎭 **Four Unique Characters**
- **Warrior**: Balanced tank with high defense
- **Mage**: Area damage specialist with magic attacks
- **Archer**: Ranged attacker with high mobility
- **Assassin**: High-speed melee damage dealer

### 🔫 **Six Different Weapons**
- **Pistol**: Balanced rapid fire
- **Shotgun**: High damage spread shots
- **Sniper Rifle**: Long-range precision
- **Flame Thrower**: Continuous fire damage
- **Laser Rifle**: Energy beam attacks
- **Recurve Bow**: Traditional archery

### 🎨 **Visual Excellence**
- Particle effects and explosions
- Screen shake on heavy hits
- Dynamic health bars with animations
- Smooth character animations
- Glowing visual effects

### 🔊 **Immersive Audio**
- Background music with volume control
- Sound effects for all actions
- Victory and defeat fanfares
- Menu navigation sounds

### 🎮 **Game Features**
- Local 2-player multiplayer
- Pause menu with settings
- Round-based gameplay
- Score tracking
- Character selection screen
- Game over screen with stats

## 📋 Requirements

- **Java 11 or higher** (JDK 11+)
- **JavaFX SDK 17 or higher**
- **Minimum 2GB RAM**
- **Dual-core processor**

## 🚀 Quick Start

### **Method 1: Using IDE (Recommended)**
1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/BattleArena.git
   cd BattleArena
Open in your favorite IDE:

IntelliJ IDEA: File → Open → Select project folder

Eclipse: File → Import → Existing Maven Project

NetBeans: File → Open Project

Configure JavaFX:

Set VM Options: --module-path "path/to/javafx-sdk/lib" --add-modules javafx.controls,javafx.media

Run the game:

Run application.Main class

Method 2: Command Line (Maven)
bash
# Clone repository
git clone https://github.com/yourusername/BattleArena.git
cd BattleArena

# Compile project
mvn clean compile

# Run game (update JavaFX path)
java --module-path "/path/to/javafx-sdk/lib" \
     --add-modules javafx.controls,javafx.media \
     -cp "target/classes:src/main/resources" \
     application.Main
Method 3: Using Provided Scripts
bash
# Windows
run.bat

# Linux/Mac
chmod +x run.sh
./run.sh
🎮 Controls
Player 1 (Blue)
Action	Key
Move Up	W
Move Down	S
Move Left	A
Move Right	D
Shoot	F
Switch Weapon	Q
Reload	1
Player 2 (Red)
Action	Key
Move Up	↑
Move Down	↓
Move Left	←
Move Right	→
Shoot	L
Switch Weapon	P
Reload	0
Game Controls
Action	Key
Pause/Resume	ESC
Music Toggle	Pause Menu
Sound Toggle	Pause Menu
Exit Game	Pause Menu
Restart Game	Game Over Screen
📊 Character Stats
Character	❤️ Health	⚡ Speed	🛡️ Defense	🗡️ Damage Type	Default Weapon
Warrior	150	Medium	High	Balanced	Pistol
Mage	100	Low	Low	Area	Flame Thrower
Archer	120	High	Medium	Ranged	Recurve Bow
Assassin	90	Very High	Low	High	Shotgun
🔫 Weapon Stats
Weapon	💥 Damage	🚀 Speed	⏱️ Cooldown	🔢 Ammo
Pistol	15	8	400ms	12
Shotgun	60	6	800ms	6
Sniper Rifle	40	15	1200ms	4
Flame Thrower	5	4	100ms	50
Laser Rifle	25	12	300ms	20
Recurve Bow	28	10	600ms	15
📁 Project Structure
text
BattleArena/
├── src/main/java/
│   ├── application/          # Main application and scenes
│   │   ├── Main.java         # Entry point
│   │   ├── SceneManager.java # Scene navigation
│   │   ├── CharacterSelectionScene.java
│   │   ├── GameScene.java    # Main gameplay
│   │   └── GameOverScene.java
│   ├── animations/           # Visual effects
│   │   ├── AnimationManager.java
│   │   ├── GameAnimations.java
│   │   ├── ParticleEffects.java
│   │   └── TransitionEffects.java
│   ├── audio/               # Audio system
│   │   ├── AudioManager.java
│   │   ├── BackgroundMusic.java
│   │   └── SoundEffect.java
│   ├── characters/          # Character system
│   │   ├── Fighter.java     # Base character class
│   │   ├── Warrior.java
│   │   ├── Mage.java
│   │   ├── Archer.java
│   │   ├── Assassin.java
│   │   └── CharacterFactory.java
│   ├── config/             # Game configuration
│   │   ├── CharacterConfig.java
│   │   ├── GameConfig.java
│   │   └── WeaponConfig.java
│   ├── input/             # Input handling
│   │   ├── ControlScheme.java
│   │   └── InputManager.java
│   ├── physics/           # Physics system
│   │   ├── Vector2D.java
│   │   ├── PhysicsEngine.java
│   │   └── CollisionDetector.java
│   ├── projectiles/       # Projectile system
│   │   ├── Projectile.java
│   │   ├── Bullet.java
│   │   ├── Arrow.java
│   │   ├── Fireball.java
│   │   └── ShotgunPellet.java
│   ├── ui/               # User interface
│   │   ├── HealthBar.java
│   │   ├── WeaponHUD.java
│   │   ├── PauseMenuUI.java
│   │   └── ScoreDisplay.java
│   └── weapons/          # Weapon system
│       ├── Weapon.java
│       ├── WeaponManager.java
│       ├── Pistol.java
│       ├── Shotgun.java
│       └── SniperRifle.java
├── src/main/resources/   # Game assets
│   ├── sounds/          # Audio files (.wav, .mp3)
│   └── icon/           # Character icons (.jpg, .png)
├── pom.xml             # Maven configuration
├── build.gradle        # Gradle configuration
├── README.md          # This file
└── .gitignore         # Git ignore rules
🎵 Adding Assets
Sound Files
Place these files in src/main/resources/sounds/:

background_music.mp3 - Game background music

shoot.wav - Weapon firing sound

hit.wav - Hit impact sound

explosion.wav - Explosion sound

weapon_switch.wav - Weapon switching sound

ability.wav - Ability activation sound

victory.wav - Victory fanfare

defeat.wav - Defeat sound

menu_select.wav - Menu navigation

menu_confirm.wav - Menu confirmation

Character Icons
Place these images in src/main/resources/icon/ (100x100px recommended):

warrior.jpg - Warrior character icon

mage.jpg - Mage character icon

archer.jpg - Archer character icon

assassin.jpg - Assassin character icon

Note: The game will work without these files but will show missing asset warnings.

🛠️ Development
Building from Source
bash
# Using Maven
mvn clean package

# Using Gradle
gradle build
Dependencies
JavaFX 17+ (Controls, Media, Graphics)

JUnit 5 (Testing - optional)

Code Style
Follow Java naming conventions

Use meaningful variable names

Add comments for complex logic

Package-private where appropriate

🤝 Contributing
Fork the repository

Create a feature branch (git checkout -b feature/AmazingFeature)

Commit your changes (git commit -m 'Add AmazingFeature')

Push to the branch (git push origin feature/AmazingFeature)

Open a Pull Request

Areas for Contribution
New character classes

Additional weapons

More visual effects

Sound design

UI improvements

Bug fixes

🐛 Troubleshooting
Issue	Solution
"JavaFX runtime components missing"	Add JavaFX SDK to module path
"No sound playing"	Check sound files in resources/sounds/
"Controls not working"	Ensure window has focus
"Game runs slowly"	Close other applications, lower screen resolution
"Icons not showing"	Check icon files in resources/icon/
📝 License
This project is licensed under the MIT License - see the LICENSE file for details.

👏 Credits
Developer: [Your Name]

Game Design: Original concept

Graphics: Custom pixel art/icons

Sound Effects: Royalty-free assets

🌟 Show Your Support
Give a ⭐️ if you like this project!

<div align="center"> Made with ❤️ and Java </div> ```
