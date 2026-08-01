# 🐇 RabbitHollow — Architecture

> **Public Architecture Overview**
>
> This document describes the high-level architecture of RabbitHollow.
> It intentionally avoids internal implementation details and security-sensitive information.

---

# 📖 Overview

RabbitHollow is designed as an **offline-first pixel-art Action RPG** built with modern web technologies.

The architecture is designed to support:

- modular game systems
- offline gameplay
- scalable content
- reusable components
- data-driven game design
- future online features

The project is structured so individual game systems can evolve independently without requiring the entire game to be rewritten.

---

# 🏗️ High-Level Architecture

The game is divided into several logical layers.

```text
┌──────────────────────────────┐
│          GAME UI             │
│ Menu · HUD · Inventory       │
│ Skills · Equipment           │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│       GAMEPLAY SYSTEMS       │
│ Combat · Skills · Loot       │
│ Quests · Progression         │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│        GAME ENTITIES         │
│ Player · Champions           │
│ Monsters · Bosses · NPCs     │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│         WORLD SYSTEM         │
│ Maps · Dungeons · Events     │
│ Collision · Navigation       │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│        CORE ENGINE           │
│ Game Loop · Scenes           │
│ Input · Assets · Audio       │
└──────────────────────────────┘
```

The architecture is intentionally modular.

Gameplay systems should not depend directly on UI components whenever possible.

---

# 🎮 Game Engine

RabbitHollow uses a browser-based 2D game architecture.

The current technology direction is:

- TypeScript
- Phaser 3
- Vite

The engine layer is responsible for the core runtime of the game.

It manages:

- game initialization
- scenes
- rendering
- input
- asset loading
- audio
- game loop

The game engine should remain independent from individual gameplay mechanics.

---

# 🧩 Scene Architecture

The game is divided into separate scenes.

A simplified example:

```text
BootScene
    ↓
PreloadScene
    ↓
MainMenuScene
    ↓
ChampionSelectScene
    ↓
WorldScene
    ↓
DungeonScene
```

Each scene has a specific responsibility.

For example:

**MainMenuScene**

Handles navigation and menu interaction.

**ChampionSelectScene**

Handles Champion selection.

**WorldScene**

Handles the main game world.

**DungeonScene**

Handles dungeon gameplay.

The exact scene structure may evolve during development.

---

# 🧙 Champion System

Champions are designed as modular entities.

A Champion contains:

```text
Champion
├── Identity
├── Stats
├── Level
├── Experience
├── Skills
├── Equipment
├── Inventory
└── Progression
```

Different Champions share common functionality while having their own gameplay behavior.

Example:

```text
Champion
│
├── Barbarian
│   ├── Berserker
│   ├── Warlord
│   └── Juggernaut
│
├── Mage
│   ├── Pyromancer
│   ├── Frostcaller
│   └── Arcanist
│
├── Rogue
│   ├── Assassin
│   ├── Shadowdancer
│   └── Ranger
│
└── Paladin
    ├── Crusader
    ├── Templar
    └── Guardian
```

The system is designed so new Champions can be added without rebuilding the entire gameplay architecture.

---

# ⚔️ Combat Architecture

Combat is separated from the visual presentation of the game.

A simplified combat flow:

```text
PLAYER INPUT
     ↓
ACTION
     ↓
ABILITY
     ↓
TARGET
     ↓
DAMAGE CALCULATION
     ↓
EFFECTS
     ↓
RESULT
```

Combat can include:

- Basic Attacks
- Skills
- Critical Hits
- Damage Types
- Status Effects
- Buffs
- Debuffs
- Shields
- Healing

The goal is to keep combat logic modular and reusable.

The same combat systems can be used by:

- Players
- Monsters
- Elites
- Bosses

---

# 👹 Entity System

Entities represent interactive objects in the game world.

Examples include:

```text
Player
Champion
Monster
Elite
Boss
NPC
Interactable Object
```

Entities can share common functionality while maintaining unique behavior.

This allows the game to introduce new enemy types without duplicating the entire entity system.

---

# 🧠 AI Architecture

Enemy AI is designed around behavior states.

A simplified example:

```text
IDLE
  ↓
PATROL
  ↓
DETECT
  ↓
CHASE
  ↓
ATTACK
  ↓
RETREAT
  ↓
DEATH
```

Different entities can implement different behavior patterns.

Examples:

- Melee AI
- Ranged AI
- Group AI
- Elite AI
- Boss AI

Bosses can use specialized behavior patterns and multiple combat phases.

The public architecture does not expose internal AI implementation details.

---

# 🌍 World Architecture

The game world consists of maps and interactive environments.

```text
WORLD
│
├── Hollowmere
├── Whispering Woods
├── Ashen Mines
├── Forgotten Ruins
└── The Hollow
```

Each region can contain:

- Maps
- NPCs
- Monsters
- Events
- Dungeons
- Bosses
- Loot

The world architecture is designed to support additional regions in the future.

---

# 🌀 Dungeon Architecture

Dungeons are designed as modular gameplay environments.

A dungeon can contain:

```text
Entrance
    ↓
Combat Room
    ↓
Event
    ↓
Elite Room
    ↓
Treasure Room
    ↓
Boss Room
```

Future dungeon generation may introduce:

- procedural layouts
- random room combinations
- random events
- dungeon modifiers
- secret rooms

The exact generation algorithms are intentionally not documented publicly.

---

# 💎 Item & Loot Architecture

Items are data-driven.

A simplified item model contains:

```text
Item
├── ID
├── Name
├── Type
├── Rarity
├── Level
├── Stats
├── Affixes
└── Enchantments
```

Loot is generated based on configured loot rules.

Possible item categories include:

- Weapons
- Armor
- Rings
- Amulets
- Potions
- Materials
- Scrolls

The system is designed to allow new item types and properties to be added over time.

---

# 🎒 Inventory & Equipment

Inventory and equipment are separate logical systems.

```text
Inventory
    ↓
Item Storage
    ↓
Equipment
    ↓
Character Stats
```

Equipping an item can affect the Champion's final statistics.

The system supports future expansion with:

- additional equipment slots
- item sets
- unique items
- legendary effects
- enchantments

---

# 📈 Progression Architecture

Character progression consists of multiple systems.

```text
Experience
    ↓
Level
    ↓
Stats
    ↓
Skills
    ↓
Equipment
    ↓
Enchantments
```

The architecture is designed to support different progression paths.

A Champion's power is not determined only by their level.

Build decisions, skills and equipment also affect gameplay.

---

# 💾 Offline-First Architecture

RabbitHollow is designed to support offline gameplay.

Local game data may include:

- Characters
- Progression
- Inventory
- Equipment
- Skills
- Quests
- Local game state

The client uses browser storage technologies for local persistence.

The current technology direction includes:

**IndexedDB**

The goal is to allow the core game to remain playable without an active internet connection.

---

# 🌐 Future Online Services

Online functionality is considered an optional extension.

Potential future services include:

```text
Game Client
     │
     ▼
Online Services
     │
     ├── Account
     ├── Cloud Save
     ├── Authentication
     └── Online Features
```

The core gameplay architecture is designed so offline gameplay does not depend entirely on online services.

Online functionality will be introduced gradually.

---

# 🔐 Authentication

Future account functionality may support external identity providers.

One possible option is:

**Google Sign-In**

Authentication would be used for optional account functionality such as:

- Cloud Save
- Account Recovery
- Cross-Device Progression

Authentication and account systems are intentionally kept separate from the core local gameplay systems.

---

# 🛡️ Security Philosophy

RabbitHollow follows a principle of minimizing trust in client-side data.

The client should not be considered inherently trusted for future online features.

Potential future online systems will require:

- server-side validation
- authenticated requests
- rate limiting
- input validation
- secure data handling

Detailed security architecture is intentionally not documented in this public overview.

---

# 🧪 Testing Architecture

Testing will be introduced alongside the development of major systems.

Potential testing layers include:

```text
Unit Tests
    ↓
System Tests
    ↓
Integration Tests
    ↓
Gameplay Testing
```

Important systems to test include:

- Combat
- Damage
- Leveling
- Loot
- Inventory
- Equipment
- Skills
- Persistence

The goal is to prevent changes in one system from unexpectedly breaking another.

---

# 📦 Data-Driven Design

Where practical, game content is separated from gameplay logic.

This allows content such as:

- Champions
- Skills
- Monsters
- Items
- Loot
- Enchantments

to be represented as structured data.

Conceptually:

```text
DATA
  ↓
GAME SYSTEM
  ↓
GAMEPLAY
```

This makes it easier to add new content without rewriting core systems.

---

# 🔄 Development Approach

RabbitHollow is developed incrementally.

The development process follows a simple cycle:

```text
DESIGN
   ↓
IMPLEMENT
   ↓
TEST
   ↓
PLAY
   ↓
IMPROVE
   ↓
REFACTOR
```

Features are introduced gradually.

The goal is to keep the project playable during development rather than waiting until the entire game is complete.

---

# 🧭 Planned Architecture Evolution

The architecture will evolve with the project.

The initial version focuses on:

```text
Single Player
Offline
Browser
Local Persistence
```

Future versions may introduce:

```text
Optional Accounts
Cloud Save
Online Services
Co-op
Multiplayer
```

These features are not required for the initial game.

The architecture is designed to leave room for them without making the first version unnecessarily complex.

---

# 🔒 Public Architecture Notice

This document intentionally provides only a high-level overview.

It does not contain:

- private credentials
- API keys
- authentication secrets
- internal infrastructure
- production server configuration
- security-sensitive implementation details
- proprietary algorithms
- private deployment information

The purpose of this document is to explain the project's architecture and development philosophy, not to expose internal implementation details.

---

# 🐇 Final Vision

RabbitHollow is designed to start small and grow over time.

The initial goal is simple:

```text
ONE CHAMPION
    ↓
ONE MAP
    ↓
ONE MONSTER
    ↓
ONE COMBAT SYSTEM
    ↓
ONE DUNGEON
```

From this foundation, the game can evolve into a much larger world.

```text
CHAMPIONS
    ↓
WORLD
    ↓
DUNGEONS
    ↓
BOSSES
    ↓
LOOT
    ↓
PROGRESSION
    ↓
ENDGAME
```

The architecture is built around one principle:

> **Build the foundation correctly, then let the world grow.**

---

<div align="center">

# 🐇 RABBIT HOLLOW

**Enter the Hollow. Become the Legend.**

</div>
