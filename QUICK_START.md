# 🚀 QUICK START - Get Your Game Live in 5 Minutes!

## What You're Getting

A complete, working voxel game platform with:
- 🎮 3D voxel world you can explore
- 📝 Built-in code editor (edit games in the browser!)
- 🏃 Character controller with physics
- 🔧 Hot reload (changes appear instantly)
- 🌐 Runs in any browser, no installation needed

---

## 5-Minute Deployment

### Step 1: Get the Files (30 seconds)

The complete game is in: `/mnt/user-data/outputs/voxel-game-edu/`

All files are ready to go - just upload them!

### Step 2: Create GitHub Repo (1 minute)

1. Go to https://github.com/new
2. Name: `voxel-game-edu`
3. Public repository
4. Click "Create repository"

### Step 3: Upload Files (2 minutes)

1. Click "uploading an existing file"
2. Drag ALL files from `voxel-game-edu` folder
3. **Important**: Include the `.github` folder!
4. Commit: "Initial commit"

### Step 4: Enable GitHub Pages (1 minute)

1. Repository → Settings → Pages
2. Source: **GitHub Actions**
3. That's it!

### Step 5: Wait & Play! (1 minute)

1. Go to Actions tab
2. Wait for green checkmark ✅
3. Visit: `https://YOUR_USERNAME.github.io/voxel-game-edu/`

---

## 🎮 First Time Playing

1. Open your game URL
2. Click **"Run"** button
3. Click on the game canvas (to capture mouse)
4. Use **WASD** to move, **Space** to jump

---

## ✏️ Make Your First Edit

1. Look at the code editor on the left
2. Find the line: `Player.color = {r = 0.3, g = 0.6, b = 1.0}`
3. Change to: `Player.color = {r = 1.0, g = 0, b = 0}` (red player!)
4. Click **"Run"** again
5. Your player is now RED! 🔴

---

## 🎯 What to Try Next

### Make the Player Jump Higher
```lua
function onAction1()
    if Player.onGround then
        Player.velocity.y = 25  -- Changed from 15 to 25
    end
end
```

### Build a Platform
```lua
function onStart()
    -- Add this code
    for x = 5, 15 do
        for z = 5, 15 do
            World.setVoxel(x, 5, z, 4)  -- Gold platform!
        end
    end
end
```

### Create Stairs
```lua
function onStart()
    for i = 0, 10 do
        for z = -2, 2 do
            World.setVoxel(i, i, z, 2)  -- Stone stairs
        end
    end
end
```

---

## 📁 File Structure

```
voxel-game-edu/
├── index.html              ← The game interface
├── package.json            ← Dependencies
├── vite.config.js          ← Build settings
├── README.md               ← Full documentation
├── .github/workflows/      ← Auto-deployment
│   └── deploy.yml
└── src/
    ├── main.js             ← Game engine
    ├── voxel-world.js      ← World rendering
    ├── player.js           ← Player physics
    └── lua-runtime.js      ← Lua integration
```

---

## 🎓 Learning Path

**Hour 1**: Move around, jump, place blocks  
**Hour 2**: Edit code, change colors and jump height  
**Hour 3**: Build platforms and structures  
**Hour 5**: Create a complete playable level  
**Hour 10**: Build a maze, platformer, or race track  

---

## 💡 Pro Tips

1. **Use print() to debug**
   ```lua
   print("Player position:", Player.position.x, Player.position.y, Player.position.z)
   ```

2. **Check the console** (Press F12)
   - All print() output appears here
   - Errors show in red

3. **Experiment freely**
   - Can't break anything!
   - Just click "Run" to reset

4. **Build incrementally**
   - Add one feature at a time
   - Test after each change

---

## 🐛 Quick Fixes

**Game won't start?**
- Check browser console (F12) for errors
- Look for typos in your Lua code

**Mouse not working?**
- Click the game canvas first
- Browser will ask permission

**Changes not appearing?**
- Click the "Run" button after editing
- Or refresh page (F5)

---

## 🎉 You're Ready!

Everything works right out of the box. Just upload to GitHub and start creating!

**Your game will be live at:**
```
https://YOUR_USERNAME.github.io/voxel-game-edu/
```

Have fun building! 🎮✨
