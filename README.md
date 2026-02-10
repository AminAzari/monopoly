# 🎲 Monopoly Classic - 8×5 Board

Play live at: https://mono110.netlify.app

A fully-featured digital Monopoly game with local multiplayer, online multiplayer, and AI opponent support. Built with vanilla JavaScript and peer-to-peer networking.

## 🎮 Game Modes

- **🤖 Play vs AI** - Challenge computer opponents
- **🌐 Online Multiplayer** - Play with friends using room codes (powered by PeerJS)
- **👥 Local Multiplayer** - Hot-seat play with 2-4 players on the same device

## 📋 How to Play

### Game Rules

#### Setup
- Each player starts with **$1500**
- Players take turns rolling dice and moving around the board
- The goal is to bankrupt your opponents by building a property empire

#### On Your Turn
1. **Roll the Dice** - Move your pawn the number of spaces shown
2. **Land on a Property**:
   - **Unowned Property**: You can buy it for the listed price or decline (triggering an auction)
   - **Your Own Property**: Nothing happens
   - **Opponent's Property**: Pay rent to the owner
3. **End Your Turn** - Pass the dice to the next player

#### Property Types

**🏘️ Properties (Colored Tiles)**
- Purchase price: Varies by property
- Build houses/hotels when you own all properties of the same color
- Rent increases with each house: Base → 2x → 4x → 8x → 16x (Hotel)

**🚂 Railroads**
- Rent multiplies based on how many railroads you own
- No building allowed

**⚡ Utilities**
- Rent is 4x or 10x the dice roll depending on ownership
- No building allowed

#### Special Tiles

- **🏁 GO**: Collect $200 when you pass or land on GO
- **🔓 Just Visiting/Jail**: Safe tile (unless you're sent to jail)
- **🎰 Luck**: Draw a card (can be good or bad!)
- **💰 Free Parking**: Collect tax pool money
- **👮 Go to Jail**: Go directly to jail, do not collect $200
- **💸 Tax**: Pay $100 or $200 depending on the tax tile

#### Jail Rules
- Get out by:
  - Paying $50 bail
  - Rolling doubles
  - Waiting 3 turns (forced out on turn 3)

#### Building
- **Houses**: Cost varies by property color
- Must own all properties in a color group to build
- Must build evenly (no property can have 2+ more houses than others in the group)
- **Hotels**: After placing 4 houses, you can upgrade to a hotel (costs another house payment)
- **Sell Buildings**: You can demolish buildings for 50% of the build cost

#### Trading
- Propose trades with other players
- Trade properties and/or cash
- Both players must agree to the trade

#### Auctions
- If you decline to buy a property, it goes to auction
- All players (including you) can bid
- Highest bidder wins
- Minimum bid starts at $10

#### Bankruptcy
- If your money goes negative, you're bankrupt
- All your properties return to the bank (unowned)
- Last player standing wins!

## 🎯 Property Information on Tiles

Each tile displays:
- **💵 Price**: Purchase cost
- **🏠 House Cost**: Cost to build one house (properties only)
- **📊 Base Rent**: Rent with no buildings
- **💰 Current Rent**: Actual rent with buildings (shown in red when houses/hotels are built)

## ⌨️ Keyboard Shortcuts

- **Space**: Roll Dice
- **Enter**: End Turn
- **B**: Buy Property / Pay Bail
- **S**: Toggle Sell Mode
- **T**: Open Trade Menu
- **H**: Build House
- **V**: Build Hotel
- **Esc**: Exit Build/Sell Mode

## 🌐 Online Multiplayer Setup

### Host a Game
1. Click "Play Online"
2. Click "Host Game"
3. Share the **room code** with your friends
4. Wait for players to join
5. Click "Start Game" when ready

### Join a Game
1. Click "Play Online"
2. Click "Join Game"
3. Enter the **room code** provided by the host
4. Wait for the host to start the game

> **Note**: Online play uses peer-to-peer connections (PeerJS). Make sure both players have stable internet connections.

## 🛠️ Technical Features

- Fully responsive design (works on mobile, tablet, desktop)
- Smooth animations and sound effects
- Real-time game state synchronization for online play
- Persistent game log showing all actions
- Color-coded player cards and pieces
- Visual indicators for buildable/sellable properties
- Auction system with live bidding

## 🎨 Board Layout

The game uses an 8×5 grid (40 tiles total) with:
- 8 property color groups
- 4 railroads
- 2 utilities
- 4 luck tiles
- Special tiles (GO, Jail, Free Parking, Go to Jail, Taxes)

## 🚀 Getting Started

Simply open `index.html` in any modern web browser. No installation or server required!

## 📱 Mobile Support

The game is fully playable on mobile devices with touch controls and responsive layout adjustments.

## 🎭 Credits

Built with:
- Vanilla JavaScript
- PeerJS for peer-to-peer networking
- CSS Grid for board layout
- Web Audio API for sound effects

---

**Enjoy the game! May the dice be ever in your favor! 🎲**
