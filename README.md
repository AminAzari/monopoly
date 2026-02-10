# Monopoly - Multiplayer Edition

A web-based Monopoly-style board game with multiple game modes and real-time multiplayer support.

## 🎮 Game Modes

### 🤖 AI Mode
Play against computer-controlled opponents with intelligent decision-making.

### 🌐 Online Multiplayer
Play with friends remotely using room codes powered by PeerJS.

### 👥 Local Multiplayer
Pass-and-play mode for 2-4 players on the same device.

## 🎯 How to Play

### Starting a Game

1. Open `index.html` in a web browser
2. Choose your game mode from the main menu
3. Select number of players (2-4)
4. Start playing!

### Game Controls

#### Keyboard Shortcuts
- **Space** - Roll dice
- **Enter** - End turn
- **B** - Buy property (or pay bail if in jail)
- **S** - Toggle sell mode
- **T** - Open trade menu
- **H** - Build house
- **V** - Build villa
- **Esc** - Exit build/sell mode

#### Mouse Controls
- Click tiles in build mode to construct houses/villas
- Click properties in sell mode to sell them
- Use on-screen buttons for all actions

### Gameplay Basics

1. **Roll the Dice**: Move around the 5×5 board
2. **Buy Properties**: Land on unowned tiles to purchase them
3. **Build Houses & Villas**: Upgrade properties with the same color
4. **Collect Rent**: Other players pay you when landing on your properties
5. **Trading**: Negotiate property swaps with other players (local/online mode)
6. **Avoid Jail**: Landing on the jail tile sends you to jail for 3 turns

### Property Groups
Properties are colored by row:
- **Brown** (Row 0) - Cheapest properties
- **Light Blue** (Row 1)
- **Pink** (Row 2)
- **Orange** (Row 3)
- **Red** (Row 4) - Most expensive properties

### Building Rules
- Must own all properties of the same color to build
- Houses must be built evenly across the color group
- Villas can only be built after all properties have houses
- Maximum: 1 house + 1 villa per property

### Special Tiles
- **🍀 Luck Tiles**: Draw a random event card (bonus or penalty)
- **🚔 Jail**: Costs $50 to bail out, or wait 3 turns

## 🔧 Trading System

### How to Trade (Local/Online Mode)

1. Press **T** or click the "Trade" button during your turn
2. Select which player to trade with
3. Choose what you're offering:
   - Cash amount
   - Properties you own
4. Choose what you want:
   - Cash from them
   - Their properties
5. Propose the trade
6. The other player accepts or rejects

### Trading Rules
- Only available in **local** and **online** multiplayer (not AI mode)
- Can only trade with human players
- Both players must have the resources they're offering
- Properties retain their houses/villas when traded

## 🌐 Online Multiplayer Setup

### Creating a Game
1. Select "Online Multiplayer"
2. Click "Create Room"
3. Share your room code with friends
4. Wait for players to join
5. Start the game when everyone is connected

### Joining a Game
1. Select "Online Multiplayer"
2. Click "Join Room"
3. Enter the room code from your friend
4. Wait for the host to start

### Connection Tips
- Ensure stable internet connection
- Room codes are case-insensitive
- If connection fails, try refreshing and creating a new room
- All players must stay connected throughout the game

## 💡 Strategy Tips

1. **Early Game**: Focus on completing color sets
2. **Build Strategically**: Houses on high-traffic areas earn more rent
3. **Cash Management**: Keep enough money for rent and bail
4. **Trading**: Use trades to complete color sets faster
5. **Jail Strategy**: Late game, staying in jail can avoid high rents

## 🐛 Known Issues & Fixes

### Trading is Disabled
If the trade button doesn't work, check that:
- You're in **local** or **online** mode (not AI mode)
- There are other human players in the game
- It's currently your turn

**Fix**: To enable trading in all modes, edit line 2170:
```javascript
// Change this:
if (gameMode !== 'local') {

// To this:
if (gameMode === 'ai') {
```

### Online Connection Issues
- Refresh the page and try a new room code
- Check your firewall settings
- Ensure all players are using the same game version

## 📋 Requirements

- Modern web browser (Chrome, Firefox, Safari, Edge)
- Internet connection (for online multiplayer only)
- No installation required - just open the HTML file!

## 🎨 Features

- ✅ Three game modes (AI, Online, Local)
- ✅ 2-4 players
- ✅ Property trading system
- ✅ House and villa building
- ✅ Luck cards with random events
- ✅ Jail mechanics
- ✅ Full keyboard shortcuts
- ✅ Mobile-responsive design
- ✅ Real-time multiplayer via PeerJS
- ✅ Colorful, modern UI

## 🎲 Winning the Game

The game ends when only one player remains solvent. The last player standing wins!

Bankruptcy occurs when you cannot pay rent, fees, or other obligations and have no properties to sell.

## 📝 Credits

Built with vanilla JavaScript, PeerJS for multiplayer connectivity, and CSS Grid for the board layout.

---

**Enjoy the game! 🎉**
