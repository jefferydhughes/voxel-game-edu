# 🚀 Deployment Guide - Voxel Game Edu

## Complete Project Ready! 

I've created a fully functional voxel game that you can deploy to GitHub Pages in minutes.

---

## 📦 What's Included

```
voxel-game-edu/
├── index.html              # Main game page with editor
├── package.json            # Dependencies
├── vite.config.js          # Build configuration
├── README.md               # Documentation
├── .gitignore              # Git ignore rules
├── .github/
│   └── workflows/
│       └── deploy.yml      # Automatic GitHub Pages deployment
└── src/
    ├── main.js             # Game engine (300 lines)
    ├── voxel-world.js      # Voxel rendering (250 lines)
    ├── player.js           # Player controller (150 lines)
    └── lua-runtime.js      # Lua integration (300 lines)
```

**Total: ~1000 lines of clean, commented code!**

---

## 🎯 Step-by-Step Deployment

### Step 1: Create GitHub Repository

1. Go to https://github.com/new
2. Name it: `voxel-game-edu` (or any name you want)
3. Make it **Public**
4. **DON'T** initialize with README (we have one)
5. Click "Create repository"

### Step 2: Upload Files

**Option A: GitHub Web Interface (Easiest)**

1. In your new repository, click "uploading an existing file"
2. Drag all files from `/mnt/user-data/outputs/voxel-game-edu/` into the upload box
3. **Important**: Make sure you upload the `.github` folder too!
4. Commit with message: "Initial commit - Complete voxel game"

**Option B: Git Command Line**

```bash
cd /mnt/user-data/outputs/voxel-game-edu
git init
git add .
git commit -m "Initial commit - Complete voxel game"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/voxel-game-edu.git
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. Go to your repository Settings
2. Click "Pages" in the left sidebar
3. Under "Build and deployment":
   - **Source**: GitHub Actions
4. That's it! The workflow will run automatically

### Step 4: Wait for Deployment

1. Go to the "Actions" tab in your repository
2. You'll see "Deploy to GitHub Pages" running
3. Wait ~2-3 minutes for it to complete
4. When it shows a green checkmark, you're live!

### Step 5: Play Your Game! 🎮

Your game will be available at:
```
https://YOUR_USERNAME.github.io/voxel-game-edu/
```

---

## 🎮 How to Play

1. **Open the URL** in your browser
2. **Click "Run"** to start the game
3. **Click on the game canvas** to capture mouse
4. **Use WASD** to move around
5. **Press Space** to jump
6. **Press E** to place blocks

### Controls

- **WASD** - Move
- **Space** - Jump (when on ground)
- **E** - Place block
- **Mouse** - Look around
- **ESC** - Release mouse cursor

---

## 📝 Editing the Game

### In the Browser

The built-in code editor lets you modify the game live:

1. Edit the Lua code in the left panel
2. Click "Run" to see your changes
3. Check the console for print() output

### Locally (For Development)

```bash
# Clone your repository
git clone https://github.com/YOUR_USERNAME/voxel-game-edu.git
cd voxel-game-edu

# Install dependencies
npm install

# Start development server
npm run dev

# Open http://localhost:3000
```

Every time you save files, changes appear instantly!

---

## 🎨 Customization Ideas

### 1. Change Player Color

```lua
function onStart()
    Player.color = {r = 1.0, g = 0, b = 0}  -- Red player
end
```

### 2. Create a House

```lua
function onStart()
    -- Floor
    for x = 0, 10 do
        for z = 0, 10 do
            World.setVoxel(x, 0, z, 1)
        end
    end
    
    -- Walls
    for y = 1, 4 do
        for x = 0, 10 do
            World.setVoxel(x, y, 0, 3)  -- Front wall
            World.setVoxel(x, y, 10, 3) -- Back wall
        end
        for z = 0, 10 do
            World.setVoxel(0, y, z, 3)  -- Left wall
            World.setVoxel(10, y, z, 3) -- Right wall
        end
    end
    
    -- Roof
    for x = 0, 10 do
        for z = 0, 10 do
            World.setVoxel(x, 5, z, 2)
        end
    end
end
```

### 3. Make a Jumping Puzzle

```lua
function onStart()
    -- Create platforms at different heights
    local platforms = {
        {x = 0, y = 0, z = 0, size = 5},
        {x = 8, y = 3, z = 2, size = 3},
        {x = 15, y = 6, z = 5, size = 3},
        {x = 22, y = 9, z = 3, size = 4},
    }
    
    for _, p in ipairs(platforms) do
        for x = p.x, p.x + p.size do
            for z = p.z, p.z + p.size do
                World.setVoxel(x, p.y, z, 1)
            end
        end
    end
    
    Player.position = {x = 2, y = 5, z = 2}
end
```

### 4. Higher Jumps

```lua
function onAction1()
    if Player.onGround then
        Player.velocity.y = 25  -- Super jump!
    end
end
```

---

## 🔧 Troubleshooting

### Game Won't Start

1. Open browser console (F12)
2. Look for errors in red
3. Common issues:
   - Lua syntax error → Check your code
   - Missing dependency → Run `npm install`

### Mouse Look Not Working

1. Click on the game canvas first
2. Your browser will ask for permission
3. Click "Allow"

### Code Changes Not Appearing

1. Click the "Run" button after editing
2. Or refresh the page (F5)

### GitHub Pages Not Updating

1. Check the Actions tab
2. Wait for deployment to finish (green checkmark)
3. Hard refresh your browser (Ctrl+Shift+R)

---

## 📚 Learning Resources

### Lua Basics

- Variables: `local x = 10`
- Functions: `function myFunc() end`
- Tables: `local t = {x = 1, y = 2}`
- Loops: `for i = 1, 10 do ... end`

### Game Development Concepts

- **Game Loop**: The `onTick()` function runs every frame
- **Physics**: Gravity pulls player down, velocity changes position
- **Collision**: Player can't go through solid voxels
- **Events**: `onAction1()` runs when you press Space

---

## 🎓 Educational Use

This platform is perfect for:

- **Computer Science classes** - Learn programming
- **Game design courses** - Understand game mechanics
- **Self-learning** - Build your own games
- **Workshops** - Teach coding through games

### Lesson Plan Ideas

1. **Hello World** - Print messages, change player color
2. **Variables** - Store and use numbers for jump height
3. **Functions** - Create reusable code (make platform function)
4. **Loops** - Build walls and floors
5. **Conditions** - Only jump when on ground
6. **Arrays** - Create multiple platforms
7. **Game Design** - Build a complete playable level

---

## 🚀 Next Steps

Want to extend the game? Here are some ideas:

### Easy
- [ ] Add more voxel types (different colors)
- [ ] Create a race track
- [ ] Build a maze
- [ ] Add a timer

### Medium
- [ ] Collectible items (coins)
- [ ] Score counter
- [ ] Multiple levels
- [ ] Sound effects

### Advanced
- [ ] Enemies that move
- [ ] Inventory system
- [ ] Save/load worlds
- [ ] Multiplayer (this requires backend)

---

## 💡 Tips for Success

1. **Start Small** - Get one thing working, then add more
2. **Test Often** - Click "Run" frequently
3. **Use print()** - Debug by printing values
4. **Read Errors** - Error messages tell you what's wrong
5. **Experiment** - Try changing numbers and see what happens

---

## 🎉 You Did It!

You now have a complete, working voxel game that:

✅ Runs in any browser  
✅ Has a built-in code editor  
✅ Supports Lua scripting  
✅ Features 3D graphics  
✅ Includes physics and collision  
✅ Deploys automatically to GitHub Pages  

**Share your game with friends and start creating!**

Your game URL:
```
https://YOUR_USERNAME.github.io/voxel-game-edu/
```

---

## 📞 Need Help?

- Check the browser console (F12) for errors
- Read the README.md for API documentation
- Look at the example code in the editor
- Experiment and have fun!

Happy coding! 🎮✨
