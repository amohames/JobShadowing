### **Collaborative Game Development Project: "Python Adventure Quest"**  
This project introduces you to game development while learning collaboration using GitHub. They will build a simple **2D adventure game** using **Pygame**, where a character explores a map, avoids obstacles, and collects items.  

This will teach them:  
✅ **Work in Teams** (Teamwork is key to success)
✅ **Game development** (graphics, animations, collision detection)  
✅ **Collaboration** (using GitHub for version control)
✅ **Software engineering practices** (branching, merging, and pull requests)  

---

## **Project Overview: "Python Adventure Quest"**  
**Game Objective:** Players control a character navigating a 2D world, avoiding obstacles, and collecting coins before time runs out.  

### **Technology Stack:**  
- **Python** (main programming language)  
- **Pygame** (game development library)  
- **GitHub** (for collaboration)  

### **Project Breakdown:**  
The game will have:  
1. A **player character** that moves with arrow keys.  
2. A **background map** (simple maze or open world).  
3. **Coins** that players collect for points.  
4. **Enemies** that players must avoid.  
5. A **timer** that ends the game when time runs out.  

---

## **Step-by-Step Project Setup**  

### **Step 1: Setting Up the Repository (Collaboration)**  
Each student will work on a different part of the game, collaborating using GitHub.  

1. One student creates a **GitHub repository**:  
   - Go to [GitHub](https://github.com/), create a new repository called `"python-adventure-quest"`.  
   - Add a README file describing the project.  

2. Other students **clone** the repository:  
   ```
   git clone https://github.com/YOUR_USERNAME/python-adventure-quest.git
   cd python-adventure-quest
   ```

3. Install **Pygame** (game development library):  
   ```
   pip install pygame
   ```

---

### **Step 2: Create a Basic Game Window**  
👨‍💻 *Assigned to: One student (Game Engine Developer)*  

- Create `game.py` with a basic game window:  
  ```python
  import pygame  

  pygame.init()  
  screen = pygame.display.set_mode((800, 600))  
  pygame.display.set_caption("Python Adventure Quest")  

  running = True  
  while running:  
      for event in pygame.event.get():  
          if event.type == pygame.QUIT:  
              running = False  

      screen.fill((0, 0, 0))  # Black background
      pygame.display.update()  

  pygame.quit()
  ```
- Test the script by running:  
  ```
  python game.py
  ```

- Commit & Push changes to GitHub:  
  ```
  git add game.py
  git commit -m "Added basic game window"
  git push origin main
  ```

---

### **Step 3: Add a Playable Character**  
👨‍💻 *Assigned to: Another student (Character Developer)*  

1. Create `player.py`:  
   ```python
   import pygame  

   class Player:
       def __init__(self, x, y):
           self.image = pygame.image.load("player.png")  # Load player image
           self.rect = self.image.get_rect(topleft=(x, y))

       def move(self, keys):
           if keys[pygame.K_LEFT]:
               self.rect.x -= 5
           if keys[pygame.K_RIGHT]:
               self.rect.x += 5
           if keys[pygame.K_UP]:
               self.rect.y -= 5
           if keys[pygame.K_DOWN]:
               self.rect.y += 5

       def draw(self, screen):
           screen.blit(self.image, self.rect)
   ```

2. Add the player to `game.py`:  
   ```python
   from player import Player  

   player = Player(400, 300)  

   while running:
       keys = pygame.key.get_pressed()  
       player.move(keys)  
       screen.fill((0, 0, 0))  
       player.draw(screen)  
       pygame.display.update()  
   ```

3. Upload `player.png` (simple character image) and commit changes:  
   ```
   git add player.py player.png
   git commit -m "Added player character"
   git push origin main
   ```

---

### **Step 4: Create a Game Map**  
👨‍💻 *Assigned to: Another student (Map Designer)*  

1. Create `map.py`:  
   ```python
   import pygame  

   class GameMap:
       def __init__(self):
           self.image = pygame.image.load("background.png")  
           self.rect = self.image.get_rect()

       def draw(self, screen):
           screen.blit(self.image, self.rect)
   ```

2. Add the map to `game.py`:  
   ```python
   from map import GameMap  

   game_map = GameMap()  

   while running:
       screen.fill((0, 0, 0))  
       game_map.draw(screen)  
       player.draw(screen)  
       pygame.display.update()
   ```

3. Upload `background.png` (game map image) and commit:  
   ```
   git add map.py background.png
   git commit -m "Added game map"
   git push origin main
   ```

---

### **Step 5: Add Collectible Coins**  
👨‍💻 *Assigned to: Another student (Item Developer)*  

1. Create `coin.py`:  
   ```python
   import pygame  
   import random  

   class Coin:
       def __init__(self):
           self.image = pygame.image.load("coin.png")
           self.rect = self.image.get_rect(center=(random.randint(50, 750), random.randint(50, 550)))

       def draw(self, screen):
           screen.blit(self.image, self.rect)
   ```

2. Add coins to `game.py`:  
   ```python
   from coin import Coin  

   coins = [Coin() for _ in range(5)]  

   while running:
       for coin in coins:
           coin.draw(screen)
   ```

3. Upload `coin.png` and commit:  
   ```
   git add coin.py coin.png
   git commit -m "Added coins"
   git push origin main
   ```

---

### **Step 6: Add Collision & Score System**  
👨‍💻 *Assigned to: Another student (Game Mechanic Developer)*  

1. Modify `player.py` to collect coins:  
   ```python
   def collect_coins(self, coins):
       for coin in coins[:]:
           if self.rect.colliderect(coin.rect):
               coins.remove(coin)
   ```

2. Modify `game.py` to keep track of score:  
   ```python
   score = 0

   while running:
       player.collect_coins(coins)
       score = 5 - len(coins)  
       print(f"Score: {score}")
   ```

3. Commit:  
   ```
   git commit -m "Added collision detection and score system"
   git push origin main
   ```

---

### **Step 7: Finalize & Playtest**  
1. Merge all branches and **playtest** together.  
2. Fix **bugs** and improve **graphics**.  
3. Add a **timer** to make it more challenging.  
4. Package the game for **friends to try**!  

---

## **What They Will Learn**
✅ **Game development basics** (player movement, collision, items).  
✅ **Collaboration** (working on different files and merging code).  
✅ **GitHub workflows** (branches, commits, pull requests).  
✅ **Problem-solving** (fixing bugs, improving gameplay).  

Would you like an extra **stretch goal** like multiplayer or AI enemies? 🚀
