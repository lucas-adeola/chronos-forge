# ChronosForge Gaming Protocol

[![Stacks](https://img.shields.io/badge/Stacks-Layer%202-purple)](https://stacks.co/)
[![Bitcoin](https://img.shields.io/badge/Built%20on-Bitcoin-orange)](https://bitcoin.org/)
[![Clarity](https://img.shields.io/badge/Language-Clarity-blue)](https://clarity-lang.org/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

> A next-generation blockchain gaming infrastructure that transforms how players experience virtual worlds through time-locked achievements, progressive NFT evolution, and cross-dimensional asset portability on Bitcoin's secure foundation.

## 🎮 Overview

ChronosForge revolutionizes gaming by introducing temporal mechanics where assets evolve and gain power over time through active gameplay. Built on Stacks Layer 2, it provides lightning-fast interactions while maintaining Bitcoin-level security for high-value gaming assets and tournament prizes.

### Key Features

- **🕐 Temporal Asset Evolution**: Assets evolve and gain power over time through active gameplay
- **⚔️ Legendary Item Forging**: Players forge items that transcend individual game boundaries
- **🏆 Cross-Game Achievement System**: Unlock exclusive content across partner ecosystems
- **💰 Decentralized Tournaments**: Real Bitcoin rewards for champions
- **🏛️ Community Governance**: Shape the future of interconnected gaming realms
- **🌐 Cross-Dimensional Portability**: Use assets across multiple virtual worlds

## 🏗️ Architecture

### Core Components

1. **Asset Management System**: NFT-based gaming assets with evolution mechanics
2. **Avatar System**: Player profiles with leveling and achievement tracking
3. **Virtual Worlds Registry**: Decentralized game worlds with entry requirements
4. **Competitive Leaderboard**: Ranking system with reward distribution
5. **Experience & Leveling**: Progressive character development
6. **Protocol Governance**: Admin controls and fee management

### Smart Contract Structure

```text
chronos-forge.clar
├── Constants & Configuration
├── Data Structures (Maps & Variables)
├── Access Control & Validation
├── NFT Definitions (Assets & Avatars)
├── Core Functionality
│   ├── Asset Management
│   ├── Avatar System
│   ├── World Management
│   ├── Leaderboard System
│   └── Reward Distribution
└── Experience Calculation System
```

## 🚀 Getting Started

### Prerequisites

- [Clarinet](https://github.com/hirosystems/clarinet) - Clarity development environment
- [Node.js](https://nodejs.org/) (v16 or higher)
- [Stacks Wallet](https://wallet.hiro.so/) for testing

### Installation

Clone the repository:

```bash
git clone https://github.com/lucas-adeola/chronos-forge.git
cd chronos-forge
```

Install dependencies:

```bash
npm install
```

Initialize Clarinet project:

```bash
clarinet check
```

### Development Setup

**Run tests**:

```bash
npm test
# or
clarinet test
```

**Format code**:

```bash
clarinet fmt
```

**Check contract**:

```bash
clarinet check
```

## 📋 Contract Functions

### Asset Management

#### `mint-chronos-asset`

Creates a new gaming asset NFT with specified attributes.

**Parameters:**

- `name`: Asset name (string-ascii 50)
- `description`: Asset description (string-ascii 200)
- `rarity`: Asset rarity ("common", "uncommon", "rare", "epic", "legendary")
- `power-level`: Power level (1-1000)
- `world-id`: Associated world ID
- `attributes`: List of asset attributes

#### `transfer-game-asset`

Transfers an asset to another player.

**Parameters:**

- `token-id`: Asset token ID
- `recipient`: Recipient principal

### Avatar System

#### `create-avatar`

Creates a new player avatar with world access.

**Parameters:**

- `name`: Avatar name (string-ascii 50)
- `world-access`: List of accessible world IDs

#### `update-avatar-experience`

Updates avatar experience and handles level progression.

**Parameters:**

- `avatar-id`: Avatar identifier
- `experience-gained`: Experience points to add

### World Management

#### `create-game-world`

Creates a new virtual world for gameplay.

**Parameters:**

- `name`: World name (string-ascii 50)
- `description`: World description (string-ascii 200)
- `entry-requirement`: Level requirement for entry

### Leaderboard & Rewards

#### `update-player-score`

Updates a player's competitive score.

**Parameters:**

- `player`: Player principal
- `new-score`: New score value (0-10000)

#### `distribute-bitcoin-rewards`

Distributes Bitcoin rewards to top players.

## 🎯 Usage Examples

### Creating an Avatar

```clarity
;; Create a new avatar with access to worlds 1 and 2
(contract-call? .chronos-forge create-avatar 
  "DragonSlayer" 
  (list u1 u2))
```

### Minting a Gaming Asset

```clarity
;; Mint a legendary sword
(contract-call? .chronos-forge mint-chronos-asset
  "Excalibur"
  "A legendary sword forged in the fires of time"
  "legendary"
  u950
  u1
  (list "sword" "fire" "legendary" "artifact"))
```

### Creating a Game World

```clarity
;; Create a new dungeon world
(contract-call? .chronos-forge create-game-world
  "Shadow Realm"
  "A dark dimension filled with ancient mysteries"
  u25)
```

## 📊 Game Mechanics

### Experience System

- **Base Experience Required**: 100 XP per level
- **Maximum Level**: 100
- **Max Experience per Level**: 1000 XP
- **Level Up Formula**: `BASE_EXPERIENCE_REQUIRED * current_level`

### Asset Rarity System

| Rarity | Power Range | Drop Rate |
|--------|-------------|-----------|
| Common | 1-200 | High |
| Uncommon | 201-400 | Medium |
| Rare | 401-600 | Low |
| Epic | 601-800 | Very Low |
| Legendary | 801-1000 | Ultra Rare |

### Reward Distribution

Rewards are calculated based on player scores:

- Minimum qualifying score: 100
- Reward multiplier: 10x score
- Maximum single reward: 100,000 units

## 🔒 Security Features

- **Access Control**: Admin whitelist for sensitive operations
- **Input Validation**: Comprehensive validation for all parameters
- **Safe Transfers**: Protected NFT transfer mechanisms
- **Principal Verification**: Secure principal validation
- **Overflow Protection**: Safe arithmetic operations

## 🧪 Testing

The project includes comprehensive test coverage:

```bash
# Run all tests
npm test

# Run specific test file
npx vitest tests/chronos-forge.test.ts

# Run tests with coverage
npm run test:coverage
```

## 📈 Roadmap

### Phase 1: Core Infrastructure ✅

- [x] Basic asset and avatar systems
- [x] World creation and management
- [x] Experience and leveling mechanics

### Phase 2: Advanced Features 🔄

- [ ] Cross-chain asset bridging
- [ ] Advanced tournament mechanics
- [ ] Governance token integration
- [ ] Community marketplace

### Phase 3: Ecosystem Expansion 📋

- [ ] Partner game integration
- [ ] Mobile wallet support
- [ ] Advanced analytics dashboard
- [ ] Decentralized governance implementation

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Development Process

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Ensure all tests pass
6. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
