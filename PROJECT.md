# 🐇 RabbitHollow — Project Vision & Development Plan

> **Enter the Hollow. Become the Legend.**

---

## 📖 O projektu

RabbitHollow je nezávislý pixel-art Action RPG projekt vytvořený s cílem vybudovat vlastní herní svět od úplného začátku.

Projekt vzniká jako experiment, osobní vývojový projekt a zároveň jako dlouhodobá ukázka toho, co lze vytvořit pomocí moderních webových technologií, TypeScriptu a open-source nástrojů.

Nejde pouze o vytvoření jednoduché hry.

Cílem je postupně vytvořit kompletní herní systém.

Od prvního pixelu.

Přes herní engine.

Až po svět plný Championů, monster, dungeonů, loot systému a dlouhodobé progression.

---

# ❓ Proč jsem RabbitHollow vytvořil

RabbitHollow vznikl z jednoduché myšlenky:

> **Co kdybych vytvořil vlastní RPG svět úplně od nuly?**

Inspirací jsou klasické Action RPG a Dungeon Crawlers, ale RabbitHollow není zamýšlený jako kopie existující hry.

Cílem je vytvořit vlastní identitu.

Vlastní svět.

Vlastní Championy.

Vlastní monstra.

Vlastní systém progresu.

A především vlastní příběh.

Projekt zároveň slouží jako praktická ukázka vývoje komplexní aplikace, kde se jednotlivé části systému postupně propojují.

---

# 🎯 Hlavní cíl projektu

Dlouhodobým cílem je vytvořit:

- Pixel-Art Action RPG
- Offline-First aplikaci
- PWA hru
- Real-time combat systém
- Champion systém
- Subclass systém
- Skill Tree
- Leveling systém
- Loot systém
- Equipment systém
- Enchantment systém
- Procedurální dungeony
- Monster AI
- Boss mechaniky
- Endgame systém

Projekt je navržen tak, aby mohl začít jako malá offline hra a postupně růst.

---

# 🧱 Jak bude RabbitHollow vznikat

RabbitHollow nebude vytvořen najednou.

Projekt bude rozdělen do jednotlivých etap.

Každá etapa musí vytvořit funkční část hry.

Nejdříve vznikne základní engine.

Poté hráč.

Potom svět.

Následně combat.

A až poté komplexnější RPG systémy.

Vývoj bude probíhat iterativně.

```text
ENGINE
   ↓
PLAYER
   ↓
WORLD
   ↓
COMBAT
   ↓
MONSTERS
   ↓
LEVELING
   ↓
SKILLS
   ↓
LOOT
   ↓
EQUIPMENT
   ↓
DUNGEONS
   ↓
BOSSES
   ↓
ENDGAME
```

---

# 🛠️ FÁZE 1 — TECHNICKÝ ZÁKLAD

První fáze vytvoří základ celé aplikace.

Použité technologie:

- TypeScript
- Phaser 3
- Vite
- Git
- GitHub

Cílem je vytvořit čistou a rozšiřitelnou architekturu.

V této fázi vznikne:

- Phaser Game Engine
- Vite Build System
- TypeScript konfigurace
- Scene systém
- Game Configuration
- Asset Loader
- základní Error Handling

Výsledek:

> Aplikace se spustí a zobrazí první herní scénu.

---

# 🎮 FÁZE 2 — MAIN MENU

Po vytvoření engine vznikne první uživatelské rozhraní.

Main Menu bude obsahovat:

- New Game
- Continue
- Settings
- About

Později:

- Account
- Cloud Save
- Premium

První verze bude jednoduchá.

Důležité je vytvořit základní navigaci mezi scénami.

---

# ⚔️ FÁZE 3 — CHAMPION SELECTION

Hráč si vybere svého Championa.

První dostupní Championi:

### 🪓 Barbarian

Silný melee bojovník.

### 🔥 Mage

Ranged magic damage dealer.

### 🗡️ Rogue

Rychlý Champion zaměřený na Critical Hits.

### 🛡️ Paladin

Hybrid mezi Tankem, Healerem a Holy Warrior.

Výběr Championu ovlivní:

- Stats
- Skills
- Resource System
- Equipment
- Combat Style

---

# 🗺️ FÁZE 4 — PRVNÍ SVĚT

Po výběru Championa bude hráč spawnován v prvním herním prostoru.

První lokací bude:

## Hollowmere

Bezpečná oblast, která bude sloužit jako první základna.

Hráč zde bude moci:

- procházet mapu
- mluvit s NPC
- nakupovat
- ukládat předměty
- měnit equipment
- připravovat se na výpravu

---

# 🧙 FÁZE 5 — PLAYER SYSTEM

V této fázi vznikne základní Player Entity.

Player bude mít:

- Position
- Movement
- HP
- Level
- EXP
- Stats
- Equipment
- Inventory

Ovládání:

```text
W / A / S / D
```

Později:

```text
Mouse
Keyboard
Gamepad
Touch
```

Cílem je vytvořit systém, který bude fungovat na desktopu i mobilních zařízeních.

---

# ⚔️ FÁZE 6 — COMBAT

Po vytvoření hráče vznikne první combat systém.

První implementace:

```text
Basic Attack
    ↓
Damage
    ↓
Enemy HP
    ↓
Enemy Death
    ↓
EXP
```

Následně přibudou:

- Critical Hits
- Attack Speed
- Dodge
- Skills
- Buffs
- Debuffs
- Status Effects

Combat bude v reálném čase.

---

# 👹 FÁZE 7 — MONSTER SYSTEM

Do hry budou přidáni první nepřátelé.

První nepřítel:

## Hollow Wolf

Bude mít:

- HP
- Damage
- Movement
- AI
- Attack
- Death
- EXP Reward
- Loot Table

Později vzniknou další typy monster.

Každé monster bude mít vlastní chování.

---

# 🧠 FÁZE 8 — MONSTER AI

AI bude postupně rozšířena.

Základní stavový systém:

```text
IDLE
  ↓
PATROL
  ↓
DETECT PLAYER
  ↓
CHASE
  ↓
ATTACK
  ↓
DEATH
```

Později:

- Ranged AI
- Group AI
- Boss AI
- Elite AI
- Special Behaviors

---

# 📈 FÁZE 9 — LEVELING

Hráč začne na:

**Level 1**

Za porážení monster bude získávat EXP.

```text
Monster
    ↓
EXP
    ↓
EXP Threshold
    ↓
LEVEL UP
```

Level Up může přidat:

- Stat Points
- Skill Points
- HP
- Damage
- New Skills

Maximální základní level:

**Level 100**

---

# 🌳 FÁZE 10 — SKILL SYSTEM

Každý Champion dostane vlastní schopnosti.

První verze:

- 1 Basic Attack
- 4 Active Skills

Skills budou mít:

- Damage
- Cooldown
- Resource Cost
- Range
- Area
- Effects

Později vznikne:

**Skill Tree**

který umožní vytvořit různé buildy.

---

# 🧬 FÁZE 11 — SUBCLASSES

Po vytvoření základního Skill systému vzniknou Subclasses.

Například:

```text
BARBARIAN
├── Berserker
├── Warlord
└── Juggernaut

MAGE
├── Pyromancer
├── Frostcaller
└── Arcanist

ROGUE
├── Assassin
├── Shadowdancer
└── Ranger

PALADIN
├── Crusader
├── Templar
└── Guardian
```

Subclass změní způsob hraní Championa.

---

# 💎 FÁZE 12 — LOOT

Monstra budou mít Loot Tables.

Po smrti může monster dropnout:

- Gold
- Equipment
- Materials
- Scrolls
- Potions

Rarity:

```text
Common
Uncommon
Rare
Epic
Legendary
Mythic
```

Loot bude postupně rozšířen o náhodné Affixes.

---

# 🛡️ FÁZE 13 — INVENTORY & EQUIPMENT

Hráč získá vlastní Inventory.

Equipment Slots:

```text
Weapon
Offhand
Helmet
Chest
Gloves
Boots
Ring
Ring
Amulet
```

Každý item bude mít vlastní data.

```text
Item ID
Name
Type
Rarity
Level
Stats
Affixes
Enchantments
```

---

# ✨ FÁZE 14 — ENCHANTMENT

Equipment bude možné vylepšovat.

Enchant systém umožní:

- zvýšit statistiky
- přidat nové vlastnosti
- vylepšit equipment
- měnit build

Enchantování bude vyžadovat:

- Gold
- Materials
- Enchant Scrolls

---

# 🌀 FÁZE 15 — DUNGEONS

Po vytvoření základních RPG systémů vzniknou Dungeony.

První verze bude obsahovat:

- Entrance
- Combat Rooms
- Elite Rooms
- Treasure Rooms
- Boss Room

Později vznikne procedurální generování.

Každý průchod bude jiný.

---

# 💀 FÁZE 16 — ELITE MONSTERS

Některá monstra budou mít speciální modifikátory.

Například:

```text
Molten
Frozen
Vampiric
Poisonous
Fast
Regenerating
Shielded
Explosive
```

Jeden Elite může mít více modifikátorů.

To vytvoří variabilitu dungeonů.

---

# 👑 FÁZE 17 — BOSSES

Každý hlavní region dostane svého Bosse.

Boss bude mít:

- více fází
- unikátní mechaniky
- speciální útoky
- vlastní loot table

První Boss:

**The Rootkeeper**

Později:

- The Molten Overseer
- The Ruined King
- Secret Bosses

---

# 🏆 FÁZE 18 — ENDGAME

Po dosažení Level 100 začne Endgame.

Plánované systémy:

- Nightmare Dungeons
- Endless Dungeons
- Dungeon Tiers
- Boss Challenges
- Daily Challenges
- Weekly Challenges

Cílem je vytvořit dlouhodobou hratelnost.

---

# 💾 FÁZE 19 — OFFLINE-FIRST

RabbitHollow bude navržen jako Offline-First aplikace.

Lokální data budou ukládána pomocí:

**IndexedDB**

Hráč bude moci hrát bez internetu.

Offline data:

- Characters
- Levels
- Inventory
- Equipment
- Skills
- Quests
- Dungeon Progress

---

# 🔐 FÁZE 20 — ACCOUNT SYSTEM

Registrace nebude povinná pro základní hraní.

Později bude možné přidat:

**Google Sign-In**

Účet může nabídnout:

- Cloud Save
- Cross-Device Progression
- Account Recovery
- Online Features

Offline hraní zůstane zachováno.

---

# 💎 FÁZE 21 — PREMIUM

RabbitHollow bude mít Free + Premium model.

Free verze bude obsahovat základní hru.

Premium může nabídnout:

- Premium Champions
- Premium Subclasses
- Extra Content
- Cosmetics
- Expanded Storage
- Cloud Save

Premium nebude založené na Pay-to-Win.

---

# 🚫 REKLAMY

RabbitHollow nebude používat agresivní reklamy.

Nebudou:

- Forced Ads
- Pop-up Ads během hraní
- Reklamy během Combat
- Reklamy po smrti

Cílem je zachovat kvalitní herní zážitek.

---

# 🌐 BUDOUCNOST

RabbitHollow začne jako Offline-First hra.

Dlouhodobě může vyrůst v rozsáhlejší herní svět.

Možné budoucí systémy:

- Multiplayer
- Co-op Dungeons
- Guilds
- Trading
- Global Events
- Leaderboards

Tyto systémy však nejsou prioritou první verze.

Nejdříve musí vzniknout kvalitní základní hra.

---

# 🧭 DEVELOPMENT PRINCIPLES

RabbitHollow bude vyvíjen postupně.

Každý nový systém musí být:

- Funkční
- Testovatelný
- Rozšiřitelný
- Oddělený od ostatních systémů
- Připravený na budoucí změny

Preferovaný přístup:

```text
Small Feature
    ↓
Test
    ↓
Integration
    ↓
Playtest
    ↓
Refactor
    ↓
Next Feature
```

Nejdříve funkčnost.

Potom optimalizace.

Potom vizuální polish.

---

# 🐇 PROČ RABBIT?

Králík je symbolem RabbitHollow.

Jeho význam není okamžitě vysvětlen.

Hráč ho může potkat během své cesty.

Může ukazovat cestu.

Může ukrývat tajemství.

Nebo může být pouze náhodným setkáním.

Pravdu o něm hráč zjistí až postupně.

---

# 🎯 KONEČNÁ VIZE

RabbitHollow nezačíná jako velká hra.

Začíná jako malý experiment.

Jeden Champion.

Jedna mapa.

Jedno monster.

Jeden útok.

Jeden dungeon.

A jeden králík.

Ale každý systém, který vznikne, bude základem pro další.

```text
ONE PLAYER
    ↓
ONE WORLD
    ↓
ONE DUNGEON
    ↓
ONE ADVENTURE
    ↓
A WHOLE WORLD
```

Cílem není vytvořit všechno najednou.

Cílem je vytvořit něco, co může postupně růst.

---

# 🐇 ENTER THE HOLLOW

RabbitHollow je cesta.

Od prvního pixelu.

K prvnímu Championovi.

K prvnímu Bossovi.

K prvnímu dungeon runu.

A možná...

až na samotné dno Hollow.

**The Hollow is waiting.**

**Are you ready?**

---

## 📌 PROJECT STATUS

**Current Stage:** Pre-Alpha

**Current Goal:** Build the first playable prototype

**Next Milestone:**

```text
Vite
↓
TypeScript
↓
Phaser 3
↓
Main Menu
↓
Champion Selection
↓
Player Movement
↓
First Map
↓
Basic Attack
↓
First Monster
↓
Combat
```

---

## 👨‍💻 DEVELOPMENT

RabbitHollow is an independent project created by **Patrik Djasník**.

The project is developed iteratively with a focus on learning, experimentation and building a complete game architecture from the ground up.

---

> **RabbitHollow**
>
> *Enter the Hollow. Become the Legend.*
