# 🎲 Mini Monopoly 5×5
Play live: https://mono110.netlify.app/
A fast-paced, strategic property trading game on a compact 5×5 grid. Buy properties, build houses and villas, collect rent, and dominate the board!

![Game Version](https://img.shields.io/badge/version-2.0-blue)
![Players](https://img.shields.io/badge/players-2--4-green)
![License](https://img.shields.io/badge/license-MIT-orange)

## 🎮 Features

### 🏗️ **Strategic Building System**
- Build on **any property** in your portfolio, not just where you land
- **Even Building Rule**: Must build evenly across connected clusters
- **Cluster Requirement**: Need 3+ connected properties to start building
- **Dynamic Costs**: Building costs scale with property row (Row 1: $100, Row 5: $400)
- Visual connection lines show your property networks

### 🎯 **Game Modes**
- 🤖 **vs AI**: Smart opponent with strategic building
- 🌐 **Online Multiplayer**: Real-time play with room codes via PeerJS
- 👥 **Local Multiplayer**: Pass-and-play for 2-4 players

### 🎲 **Randomized Gameplay**
- **Random Special Tiles**: Jail and Luck tiles randomize each game
- **Two Dice**: Roll 2-12 with classic probability distribution
- **Balanced Economy**: $1,500 starting cash, $100 salary

### 💎 **Quality of Life**
- ⌨️ **Keyboard Shortcuts**: SPACE (roll), ENTER (end turn), H (build), S (sell), B (buy/bail)
- 📋 **Export Logs**: Download complete game history for analysis
- 🎨 **Clean UI**: Simplified player panels showing cash and wealth
- 📱 **Mobile-Friendly**: Responsive design works on phones/tablets

---

## 🚀 Quick Start

### Play Instantly
1. Download `mini-monopoly-complete-final.html`
2. Open in any modern web browser
3. No installation required!

### Or Clone & Play
```bash
git clone https://github.com/yourusername/mini-monopoly.git
cd mini-monopoly
# Open mini-monopoly-complete-final.html in your browser
```

---

## 📖 How to Play

### 🎯 Objective
Accumulate the most wealth (cash + property value) by buying properties, building houses/villas, and collecting rent.

### 🎲 Turn Structure
1. **Roll Dice** [SPACE] - Move 2-12 tiles
2. **Take Actions**:
   - Buy unowned property [B]
   - Build houses/villas [H] - Click any eligible property
   - Sell assets [S] - Click properties to sell
3. **End Turn** [ENTER] - Pass to next player

### 🏘️ Property System

#### Buying
Land on unowned property → Press [B] to purchase

#### Building Requirements
- Must own **3+ connected properties** (horizontal/vertical adjacency)
- **Even Building**: Can't build if other tiles in cluster have fewer houses
- Example: Cluster with 2/1/1 houses → can only build on tiles with 1 house

#### Building Progression
1. Empty → House #1 ($100-$400 depending on row)
2. House #1 → House #2 (same cost)
3. House #2 → House #3 (same cost)
4. House #3 → **Villa** (same cost as house)

**Total for Villa on Row 5**: $400 × 4 = $1,600

### 💰 Economics

| Row | Property Price | House Cost | Base Rent |
|-----|---------------|------------|-----------|
| 1 🟤 | $100 | $100 | $10 |
| 2 🔵 | $150 | $150 | $20 |
| 3 🩷 | $200 | $200 | $30 |
| 4 🟠 | $300 | $300 | $50 |
| 5 🔴 | $400 | $400 | $70 |

#### Rent Multipliers
- **Empty**: 1× base rent
- **1 House**: 2× base rent
- **2 Houses**: 3× base rent
- **3 Houses**: 4× base rent
- **Villa**: **6× base rent**

*Example: Villa on Row 5 = $70 × 6 = **$420 rent***

### 🚔 Prison (Randomized Location)
Landing on the Prison tile:
- **Locked for 3 turns**
- **Option 1**: Wait 3 turns (counter decrements each turn)
- **Option 2**: Pay $300 bail [B] anytime
- Can still sell assets while in jail
- Can end turn to skip [ENTER]

### 🍀 Luck Tiles (3 Random Locations)
- Random gain/loss: **±$30 to ±$100**
- 50/50 chance positive or negative
- Triggers automatically on landing

---

## 🎮 Game Modes

### 🤖 AI Mode
- Smart opponent builds strategically
- Manages money conservatively
- Pays bail when advantageous

### 🌐 Online Multiplayer
**Host:**
1. Click "Play Online" → "Create Room"
2. Share 6-digit room code with friend
3. Wait for connection

**Join:**
1. Click "Play Online"
2. Enter room code
3. Game starts automatically

**Tech**: Peer-to-peer via PeerJS (no server needed)

### 👥 Local Multiplayer
1. Click "Local Multiplayer"
2. Choose 2, 3, or 4 players
3. Pass device between turns

**Player Colors:**
- 🔵 Player 1: Blue (Circle)
- 🔺 Player 2: Red (Triangle)
- 🟩 Player 3: Green (Square)
- 🟧 Player 4: Orange (Diamond)

---

## ⌨️ Keyboard Shortcuts

| Key | Action |
|-----|--------|
| **SPACE** | Roll Dice |
| **ENTER** | End Turn |
| **B** | Buy Property / Pay Bail |
| **H** | Toggle Build Mode |
| **S** | Toggle Sell Mode |

---

## 🎨 Building Mechanics Deep Dive

### Cluster Detection
Properties must be **connected horizontally or vertically** (not diagonal).

**Valid 3-Tile Clusters:**
```
▓▓▓     ▓      ▓▓
        ▓      ▓
        ▓
Line    L      T-shape
```

### Even Building Rule

**Scenario**: You own tiles 5, 6, 7 (horizontal line)

**State**: Houses are 2/1/0
- ❌ Cannot build on tile 5 (already has 2)
- ❌ Cannot build on tile 6 (tile 7 needs to catch up)
- ✅ Can only build on tile 7 → becomes 2/1/1

**State**: Houses are 1/1/1
- ✅ Can build on any tile → becomes 2/1/1 or 1/2/1 or 1/1/2

**Why?** Prevents "power stacking" on single properties. Encourages balanced cluster development.

### Visual Building System
1. Press [H] to enter Build Mode
2. All buildable properties **glow green**
3. Click any glowing property
4. Game automatically builds house or upgrades to villa
5. If building violates even rule, shows error message

---

## 💾 Export Logs

Click **"📋 Export Logs"** button to download:
- Complete game state snapshot
- All player data (money, position, properties)
- Full turn-by-turn history
- JSON-formatted for easy parsing

**Use cases:**
- Analyze winning strategies
- Debug issues
- Review close games
- Track statistics

---

## 🏆 Winning Strategy

### Early Game (Turns 1-5)
- **Buy aggressively** in Rows 3-4 (balanced price/rent)
- Focus on forming **3+ connected clusters**
- Avoid Row 5 unless you have spare cash

### Mid Game (Turns 6-15)
- **Build houses evenly** across your best cluster
- Keep $500+ cash reserve for rent/bail
- Monitor opponent's clusters

### Late Game (Turns 16+)
- **Rush villas** on high-rent properties
- Force opponents into bankruptcy
- Sell strategically if desperate

### Pro Tips
- **Corner clusters** are harder to complete (fewer adjacent tiles)
- **Row 3-4** offers best ROI (price vs rent ratio)
- **Jail strategy**: Pay bail early game, wait late game
- **Connection lines** show cluster boundaries at a glance

---

## 🛠️ Technical Details

### Technologies
- **Pure HTML/CSS/JavaScript** - No frameworks
- **PeerJS** - WebRTC for online multiplayer
- **localStorage** - Not used (privacy-focused)

### Browser Support
- ✅ Chrome/Edge (recommended)
- ✅ Firefox
- ✅ Safari
- ✅ Mobile browsers

### Performance
- Optimized for 60fps rendering
- Handles 4 players smoothly
- File size: ~90KB (no external dependencies except PeerJS)

### Customization
Edit constants in `<script>` section:
```javascript
const START = 1500;        // Starting money
const SALARY = 100;        // Pass Start bonus
const BAIL_AMOUNT = 300;   // Jail bail cost
const LUCK_MIN = 30;       // Min luck amount
const LUCK_MAX = 100;      // Max luck amount
const ROW_PRICES = [100, 150, 200, 300, 400];
const ROW_HOUSE_COSTS = [100, 150, 200, 300, 400];
```

---

## 📋 Game Rules Summary

### Starting Conditions
- 💰 **$1,500** starting cash
- 🎲 **2 dice** (2-12 range)
- 🏁 Start at Tile 0

### Special Tiles
- 🚔 **Prison**: 1 random tile (miss 3 turns or pay $300)
- 🍀 **Luck**: 3 random tiles (±$30-100)

### Building Rules
- ✅ Need 3+ connected properties
- ✅ Must build evenly across cluster
- ✅ Can build on any eligible property (not just where you land)
- ✅ Max 3 houses per property, then upgrade to villa

### Selling
- 💵 **80% refund** on all sales
- 💸 Can sell houses, villas, or entire properties
- 🔄 **Bankruptcy auto-sells** cheapest assets first

### Turn Flow
1. Roll dice (or pay bail if in jail)
2. Move and handle tile (buy/rent/luck)
3. Build/sell as desired
4. End turn when ready

---

## 🐛 Troubleshooting

### Online Connection Issues
- **Firewall**: Ensure WebRTC isn't blocked
- **Room Code**: Must be exact 6 digits
- **Browser**: Try Chrome/Edge for best compatibility

### Performance Issues
- Close other browser tabs
- Refresh page
- Disable browser extensions

### Logs Not Exporting
- Allow downloads in browser settings
- Check popup blocker

---

## 📝 Version History

### v2.0 (Current)
- ✨ Build on any eligible property
- ✨ Even building rule
- ✨ 2-4 player support
- ✨ Randomized special tiles
- ✨ Row-based building costs
- ✨ Turn persists until manual end

### v1.0
- Initial release
- 2-player support
- Basic building mechanics
- Fixed special tile locations

---

## 🤝 Contributing

Contributions welcome! Areas for improvement:
- [ ] AI difficulty levels
- [ ] Game statistics tracking
- [ ] Tournament mode
- [ ] Custom board sizes
- [ ] Trading system
- [ ] Animated token movement
- [ ] Sound effects expansion
- [ ] Mobile app wrapper

---

## 📄 License

MIT License - Feel free to use, modify, and distribute!

---

## 🙏 Credits

**Inspired by**: Classic Monopoly™ (Hasbro)

**Built with**: Vanilla JavaScript, PeerJS

**Special Thanks**: Claude AI for assistance in development

---

## 📞 Support

Found a bug? Have a feature request?
- 🐛 Open an issue on GitHub
- 💬 Start a discussion
- ⭐ Star the repo if you enjoy it!

---

**Happy Playing! 🎲🏠**
