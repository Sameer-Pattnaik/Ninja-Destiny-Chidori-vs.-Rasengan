## **Documentation: Ninja Destiny: Chidori vs. Rasengan**

### **Overview**
This game, "Ninja Destiny: Chidori vs. Rasengan," is a two-player-inspired game where Naruto and Sasuke battle it out. The player (Naruto) must attack Sasuke using shurikens while avoiding hits. Sasuke moves automatically and can damage Naruto upon collision.

---

### **Dependencies**
The game uses the **`pygame`** library for rendering, sound effects, and game logic. Make sure to install it using:
```bash
pip install pygame
```

---

### **Game Assets**
The game requires the following assets:
- **Images** for characters, background, and effects.
- **Sound files** for background music and hit effects.

#### Asset Folder Structure:
```
photos/
├── NR1.png       # Naruto's standing-right pose
├── NR2.png       # Naruto's walking-right pose 1
├── NR3.png       # Naruto's walking-right pose 2
├── NL1.png       # Naruto's standing-left pose
├── NL2.png       # Naruto's walking-left pose 1
├── NL3.png       # Naruto's walking-left pose 2
├── SR1.png       # Sasuke's standing-right pose
├── SR2.png       # Sasuke's walking-right pose 1
├── SR3.png       # Sasuke's walking-right pose 2
├── SL1.png       # Sasuke's standing-left pose
├── SL2.png       # Sasuke's walking-left pose 1
├── SL3.png       # Sasuke's walking-left pose 2
├── Nstanding.png # Naruto's idle position
├── Nh.png        # Naruto's health bar icon
├── Sh.png        # Sasuke's health bar icon
├── Sd.png        # Sasuke defeated image
├── Nd.png        # Naruto defeated image
├── shur.png      # Shuriken weapon image
├── bg.png        # Background image
├── hit.wav       # Hit sound effect
└── death_note.mp3 # Background music
```

---

### **Code Components**

#### **1. Player Class (`player`)**
Represents Naruto's movements, animations, and health.
- **Attributes:**
  - `x`, `y`: Position of Naruto.
  - `width`, `height`: Size of the player sprite.
  - `speed`: Movement speed.
  - `isjump`: Boolean indicating if Naruto is jumping.
  - `jumpheight`: Height of the jump.
  - `left`, `right`: Movement direction.
  - `health`: Health of Naruto.
- **Methods:**
  - `draw(win)`: Renders Naruto on the screen and displays the health bar.
  - `hit()`: Reduces Naruto's health upon collision with Sasuke.

#### **2. Weapons Class (`weapons`)**
Represents shurikens Naruto throws.
- **Attributes:**
  - `x`, `y`: Position of the shuriken.
  - `width`, `height`: Size of the shuriken.
  - `facing`: Direction of the shuriken (-1 for left, 1 for right).
  - `vel`: Velocity of the shuriken.
- **Methods:**
  - `draw(win)`: Renders the shuriken.

#### **3. Enemy Class (`enemy`)**
Represents Sasuke's movements, animations, and health.
- **Attributes:**
  - `x`, `y`: Position of Sasuke.
  - `width`, `height`: Size of the Sasuke sprite.
  - `end`: Endpoint of Sasuke's patrol path.
  - `speed`: Movement speed of Sasuke.
  - `health`: Health of Sasuke.
- **Methods:**
  - `draw(win)`: Renders Sasuke on the screen and displays the health bar.
  - `move()`: Moves Sasuke between two points.
  - `hit()`: Reduces Sasuke's health when hit by a shuriken.

#### **4. Main Game Loop**
- Handles input for movement (`K_LEFT`, `K_RIGHT`, `K_UP`) and attacking (`K_SPACE`).
- Detects collisions between:
  - Naruto and Sasuke.
  - Sasuke and shurikens.
- Updates the game window and animations using the `redrawgamewindow()` function.

#### **5. Sound and Music**
- Background music (`death_note.mp3`) plays continuously.
- Sound effects (`hit.wav`) trigger on successful hits.

---

### **How to Run the Game**
1. Install **`pygame`**:
   ```bash
   pip install pygame
   ```
2. Ensure the **`photos/`** folder and all required assets are in the same directory as the script.
3. Run the script:
   ```bash
   python ninja_game.py
   ```

---

### **Adding Pictures**

#### **Steps to Include Pictures in the Documentation:**
1. **Prepare Images:** Take screenshots or export the necessary assets, such as the game interface, character sprites, and health bars.
2. **Embed Images:** Save the images in the documentation folder and reference them like this:
   ```markdown
   ![Game Screenshot](photos/game_screenshot.png)
   ```
3. **Example Sections:**
   - **Naruto vs. Sasuke:**
     https://static1.srcdn.com/wordpress/wp-content/uploads/2022/12/naruto-sasuke.jpg

#### **Tips for Screenshots:**
- Use the `pygame.image.save()` function to capture game screenshots directly:
  ```python
  pygame.image.save(win, "photos/game_screenshot.png")
  ```

---

### **Possible Enhancements**
1. **Add Multiplayer Mode:** Allow a second player to control Sasuke.
2. **Improve Visuals:** Add advanced animations for attacks like Rasengan and Chidori.
3. **Power-Ups:** Include items that restore health or boost speed temporarily.
4. **Boss Battle:** Add other characters as unlockable bosses.
5. **High Scores:** Display the winner's score at the end of the game.


