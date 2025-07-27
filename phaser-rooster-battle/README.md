# 🐓 Rooster Battle - Phaser.js Game

A Pokemon-style battle game featuring roosters, built with Phaser.js 3.90. This is a standalone version extracted from the Telegram Mini App.

## 🎮 Game Features

- **Pokemon-style Battle System**: Turn-based combat with move selection
- **Rooster Types**: Fire (Embawk) vs Electric (Boltick) 
- **Battle Mechanics**: 
  - 4 different moves: Fire Blast, Peck, Wing Attack, Roost
  - HP bars with color-coded health (Green → Yellow → Red)
  - Damage calculation based on stats
  - Healing abilities
  - Battle animations and effects

## 🚀 Quick Start

### Option 1: Simple HTTP Server
```bash
# Navigate to the game directory
cd phaser-rooster-battle

# Install dependencies (optional)
npm install

# Start the game server
npm start
```

### Option 2: Live Development Server
```bash
# For development with auto-reload
npm run dev
```

### Option 3: Direct File Opening
Simply open `index.html` in your web browser (some features may be limited due to CORS).

## 📁 Project Structure

```
phaser-rooster-battle/
├── index.html          # Main HTML file
├── js/
│   └── game.js         # Main game logic
├── package.json        # Project configuration
└── README.md          # This file
```

## 🎯 Game Controls

- **Click** on move buttons to select attacks
- **Hover** over moves to see descriptions
- **Fire Blast**: High damage fire attack
- **Peck**: Quick normal attack
- **Wing Attack**: Flying-type attack
- **Roost**: Heal 25% of max HP

## 🛠 Customization

### Adding New Roosters
Edit the rooster data in `js/game.js`:

```javascript
this.playerRooster = {
    name: 'YourRooster',
    type: 'YourType',
    hp: 100,
    maxHp: 100,
    stats: {
        strength: 85,
        speed: 70,
        stamina: 75,
        defense: 65,
        intelligence: 70
    }
};
```

### Adding New Moves
Add to the moves array:

```javascript
this.moves = [
    { name: 'New Move', power: 30, type: 'Fire', description: 'A new powerful attack' },
    // ... existing moves
];
```

### Changing Graphics
Replace the placeholder colored squares by modifying the `preload()` function:

```javascript
// Replace this:
this.add.graphics()
    .fillStyle(0xff0000)
    .fillRect(0, 0, 64, 64)
    .generateTexture('player-rooster', 64, 64);

// With actual sprite loading:
this.load.image('player-rooster', 'assets/embawk.png');
```

## 🎨 Adding Assets

1. Create an `assets/` folder
2. Add your sprite images (PNG/JPG)
3. Update the `preload()` function to load real images instead of generated textures
4. Recommended sprite size: 64x64 pixels for roosters

## 🌐 Deployment Options

### GitHub Pages
1. Push to GitHub repository
2. Enable GitHub Pages in repository settings
3. Game will be available at: `https://yourusername.github.io/rooster-battle-phaser/`

### Netlify
1. Drag and drop the entire folder to Netlify
2. Instant deployment with custom domain support

### Traditional Web Hosting
Upload all files to your web server's public directory.

## 🔧 Development

### Local Development
```bash
# Install live-server globally for better development experience
npm install -g live-server

# Run with auto-reload
live-server --port=8080
```

### Adding Features
The game is structured with a main `RoosterBattleGame` class. Key methods:

- `preload()`: Load game assets
- `create()`: Initialize game objects
- `useMove()`: Handle player moves
- `enemyTurn()`: AI opponent logic
- `calculateDamage()`: Battle mechanics

## 📱 Mobile Support

The game is responsive and works on mobile devices. Touch events are automatically handled by Phaser.js.

## 🎮 Extending the Game

### Multiplayer Support
To add multiplayer functionality:
1. Integrate with Socket.io for real-time communication
2. Replace `enemyTurn()` with network player input
3. Add lobby system for matchmaking

### Blockchain Integration
To add Web3 features:
1. Include Web3.js or Ethers.js
2. Add wallet connection
3. Implement wager system with smart contracts

## 📄 License

MIT License - Feel free to use and modify for your projects!

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 🐛 Troubleshooting

### Game Not Loading
- Check browser console for errors
- Ensure you're running from a web server (not file://)
- Verify Phaser.js CDN is accessible

### Performance Issues
- Reduce animation complexity
- Optimize sprite sizes
- Consider using Phaser's built-in performance monitoring

---

**Enjoy battling with your roosters!** 🐓⚔️🐓
