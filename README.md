# Kyva Online (会VA)
## Strategic Fantasy RPG

### Etymology
- **Name Origin**: Kyva (pronounced "KAI-va")
- **Japanese Element**: 会 (kai) - meaning "meeting" or "assembly"
- **VA Element**: Derived from Latin "via" (path/way)
- **Significance**: Represents the meeting point of strategic gameplay and community assembly

## Table of Contents
1. [Game Introduction](#game-introduction)
2. [Getting Started](#getting-started)
3. [Character Development](#character-development)
4. [Combat Systems](#combat-systems)
5. [Faction System](#faction-system)
6. [Social Features](#social-features)
7. [Economy & Trading](#economy--trading)
8. [Progression Systems](#progression-systems)

## Other documentations
1. [Technical Architecture](./TECHNICAL-ARCHITECTURE-DOCUMENTATION.md)
2. [Gameplay Architecture](./GAMEPLAY-ARCHITECTURE.md)

## Game Introduction

Kyva Online is a strategic RPG that emphasizes tactical combat, versatile character building, and social interaction. Players can continuously adapt their playstyle through different equipment and skill combinations, participate in various PvE and PvP content, and engage in a player-driven economy.

### Core Game Features
- Tactical turn-based combat
- Dynamic equipment and skill system
- Four distinct factions
- Player-driven economy
- Guild and social systems
- Ranked PvP with strategic elements

## Getting Started

### Initial Character Setup
1. **Beginning the Journey**
   - Selection of initial equipment loadout
   - Choice of 6 beginner skills
   - Basic tutorial guidance
   - Faction personality quiz

2. **Core Statistics**
   - Strength (STR): Physical damage and combat power
   - Intelligence (INT): Magical proficiency and spell power
   - Dexterity (DEX): Speed, accuracy, and evasion
   - Vitality (VIT): Health and defensive capabilities
   - Wisdom (WIS): Resource management and skill effectiveness

```mermaid
flowchart TB
    Start[New Character]
    
    Start --> Initial[Initial Setup]
    Initial --> Equipment[Equipment Choice]
    Initial --> Skills[6 Beginner Skills]
    Initial --> Tutorial[Tutorial Phase]
    Initial --> Quiz[Faction Quiz]
    
    Equipment --> LoadoutSystem["Basic Loadout:
    - Weapon
    - Armor
    - Accessories"]
    
    Skills --> SkillSystem["Skill Selection:
    - Combat abilities
    - Utility skills
    - Basic combinations"]
    
    Tutorial --> Learning["Game Basics:
    - Combat tutorial
    - System overview
    - Basic mechanics"]
    
    Quiz --> FactionPlace["Faction Assignment:
    - Personality analysis
    - Trait matching
    - Faction placement"]
```

## Combat Systems

### PvE Combat
```mermaid
flowchart TB
    PvE[PvE Combat System]
    Single[Single Target Combat]
    Multi[Multiple Targets]
    Boss[Boss Encounters]
    
    PvE --> Single
    PvE --> Multi
    PvE --> Boss
    
    Single --> SingleDetails["6-skill loadout
    Basic rewards
    Experience gain"]
    
    Multi --> MultiDetails["AOE strategies
    Multiple mob management
    Efficient farming"]
    
    Boss --> BossDetails["Group coordination
    Premium rewards
    High-risk combat"]
```

#### PvE Features
1. **Combat Mechanics**
   - 6-skill loadout system for all encounters
   - Strategic mob engagement
   - AOE combat capabilities
   - Boss raid mechanics

2. **Rewards**
   - Equipment drops
   - Materials
   - Experience points
   - In-game currency
   - Premium currency (rare)
   - New skills (from specific encounters)

### PvP Systems
```mermaid
flowchart TB
    PvP[PvP Systems]
    
    PvP --> Normal[Normal PvP]
    PvP --> Ranked[Ranked PvP]
    
    Normal --> Offline[Offline Mode]
    Normal --> Online[Online Mode]
    
    Offline --> OfflineFeatures["Default loadout
    6 preset skills
    Automated combat"]
    
    Online --> OnlineFeatures["Free loadout choice
    All available skills
    Real-time combat"]
    
    Ranked --> RankedNormal[Standard Ranked]
    Ranked --> RankedSync[Synchronized Ranked]
    
    RankedNormal --> RankedProcess["1. RPS for first turn
    2. Loadout bans
    3. Skill bans
    4. 6 skill selection"]
    
    RankedSync --> SyncFeatures["Equalized gear stats
    Same ban system
    Pure strategy focus"]
```

#### PvP Modes Detail

1. **Normal PvP**
   - **Offline Mode**
     - Uses player's preset defensive loadout
     - Automated combat using preset 6 skills
     - Other players can challenge your offline character
   
   - **Online Mode**
     - Real-time combat between players
     - Free choice of equipment and skills
     - No banning phase
     - Similar to PvE combat mechanics

2. **Ranked PvP**
   - **Standard Ranked**
     - Rock-Paper-Scissors for first turn
     - Loadout banning phase
     - Skill banning system (based on skill count):
       - 7 skills: Ban 1
       - 8 skills: Ban 2
       - 9+ skills: Ban 3
     - Turn-based skill selection (2 skills per turn until 6 total)
     - Combat based on speed and stat calculations
   
   - **Normalized Ranked**
     - Same rules as Standard Ranked
     - Equalized gear stats
     - Focus on pure strategy and skill

### Skill System
```mermaid
flowchart TB
    Skills[Skill System]
    
    Skills --> Initial[Starting Skills]
    Skills --> Acquisition[Skill Acquisition]
    Skills --> Usage[Skill Usage]
    
    Initial --> StartingSet["6 beginner skills
    Basic loadout choice
    Tutorial guidance"]
    
    Acquisition --> Methods["Store purchase
    PvE drops
    Quest rewards
    Trading
    Premium shop"]
    
    Usage --> LoadoutSystem["6 skill loadout
    Tactical selection
    Situational adaptation"]
```

## Faction System
```mermaid
flowchart TB
    Factions[Faction System]
    
    Factions --> Snake[Snake Faction]
    Factions --> Eagle[Eagle Faction]
    Factions --> Owl[Owl Faction]
    Factions --> Raven[Raven Faction]
    
    Snake --> SnakeDetails["Primary: Cunning, Selfish, Cautious
    Values: Self-preservation, Advantage
    Style: Opportunistic combat"]
    
    Eagle --> EagleDetails["Primary: Proud, Decisive, Ambitious
    Values: Excellence, Leadership
    Style: Direct engagement"]
    
    Owl --> OwlDetails["Primary: Wise, Patient, Observant
    Values: Harmony, Understanding
    Style: Tactical approach"]
    
    Raven --> RavenDetails["Primary: Analytical, Resourceful
    Values: Knowledge, Self-reliance
    Style: Strategic combat"]
```

### Faction Details

1. **Snake Faction**
   - Primary Traits: Cunning, Selfish, Cautious
   - Secondary Traits: Deceptive, Opportunistic, Survivalist
   - Values: Self-preservation, Advantage, Secrecy

2. **Eagle Faction**
   - Primary Traits: Proud, Decisive, Ambitious
   - Secondary Traits: Competitive, Charismatic, Direct
   - Values: Excellence, Leadership, Achievement

3. **Owl Faction**
   - Primary Traits: Wise, Patient, Observant
   - Secondary Traits: Empathetic, Balanced, Diplomatic
   - Values: Wisdom, Harmony, Understanding

4. **Raven Faction**
   - Primary Traits: Analytical, Resourceful, Independent
   - Secondary Traits: Strategic, Practical, Adaptable
   - Values: Knowledge, Self-reliance, Versatility

### Faction Features
- Monthly faction change option
- Premium currency for immediate change
- Visible faction badges
- Faction-specific quests
- Faction-based achievements

## Social Features

### Guild System
```mermaid
flowchart TB
    Guild[Guild System]
    Management[Management Features]
    Wars[Guild Wars]
    Social[Social Features]
    
    Guild --> Management
    Guild --> Wars
    Guild --> Social
    
    Management --> ManagementFeatures["Player roles
    Guild ranks
    Resource management"]
    
    Wars --> WarFeatures["Guild vs Guild
    Territory control
    Guild rankings"]
    
    Social --> SocialFeatures["Guild chat
    Guild events
    Achievement tracking"]
```

#### Guild Features Detail
- Player-managed organization
- Hierarchical role system
- Internal resource management
- Guild vs Guild warfare
- Guild achievement tracking
- Guild rankings and rewards

### Trading System
```mermaid
flowchart TB
    Trading[Trading System]
    Direct[Direct Trading]
    Market[Market Trading]
    Materials[Material Exchange]
    
    Trading --> Direct
    Trading --> Market
    Trading --> Materials
    
    Direct --> DirectFeatures["Player-to-player
    Secure trade window
    Item verification"]
    
    Market --> MarketFeatures["Auction house
    Buy orders
    Sell listings"]
    
    Materials --> MaterialFeatures["Resource trading
    Bulk exchange
    Material conversion"]
```

### Communication Systems
- Guild chat system
- Friend chat system
- Discord community integration
- Trading communication
- Combat coordination

## Economy Systems

### Currency Types
1. **Regular Currency**
   - Earned through PvE
   - Trading rewards
   - Quest completion
   - Achievement rewards

2. **Premium Currency**
   - Special purchases
   - Premium features
   - Faction changes
   - Exclusive items
   - Can be traded

### Market Systems
```mermaid
flowchart TB
    Market[Market Systems]
    Player[Player Market]
    Shop[Game Shop]
    Premium[Premium Shop]
    
    Market --> Player
    Market --> Shop
    Market --> Premium
    
    Player --> PlayerTrades["Equipment trading
    Material trading
    Currency exchange"]
    
    Shop --> ShopItems["Basic equipment
    Common materials
    Regular skills"]
    
    Premium --> PremiumItems["Premium skills
    Rare items
    Convenience items"]
```

## Progression Systems

### Equipment Progression
```mermaid
flowchart TB
    Equipment[Equipment System]
    Level[Leveling System]
    Quality[Quality Enhancement]
    Crafting[Crafting System]
    
    Equipment --> Level
    Equipment --> Quality
    Equipment --> Crafting
    
    Level --> LevelFeatures["Experience based
    Stat increases
    Skill requirements"]
    
    Quality --> QualityFeatures["Level requirements
    Material fusion
    Stat multiplication"]
    
    Crafting --> CraftingFeatures["Material gathering
    Recipe discovery
    Stat customization"]
```

#### Quality Enhancement Process
1. Reach required level threshold
2. Collect necessary materials
3. Perform fusion process
4. Gain improved statistics
5. Unlock new potential

### Skill Progression
```mermaid
flowchart TB
    Skills[Skill System]
    
    Skills --> Initial[Starting Skills]
    Skills --> Acquisition[Skill Acquisition]
    Skills --> Usage[Skill Usage]
    
    Initial --> StartingSet["6 beginner skills
    Basic loadout choice
    Tutorial guidance"]
    
    Acquisition --> Methods["Store purchase
    PvE drops
    Quest rewards
    Trading
    Premium shop"]
    
    Usage --> LoadoutSystem["6 skill loadout
    Tactical selection
    Situational adaptation"]
```

## Achievement System

```mermaid
flowchart TB
    Achieve[Achievement System]
    Combat[Combat Achievements]
    Social[Social Achievements]
    Ranking[Ranking Achievements]
    
    Achieve --> Combat
    Achieve --> Social
    Achieve --> Ranking
    
    Combat --> CombatAchieve["PvE milestones
    PvP victories
    Boss defeats"]
    
    Social --> SocialAchieve["Guild participation
    Trading milestones
    Faction contributions"]
    
    Ranking --> RankAchieve["Monthly rankings
    Season rewards
    Special titles"]
```

### Monthly Rankings and Rewards

#### Ranking Categories
1. **PvP Rankings**
   - Standard ranked ladder
   - Normalized ranked ladder
   - Monthly rewards tier
   - Special titles and badges

2. **PvE Rankings**
   - Boss clear times
   - Farming efficiency
   - Challenge completions
   - Special achievements

3. **Economic Rankings**
   - Trading volume
   - Market participation
   - Material conversion
   - Crafting achievements

#### Monthly Rewards
```mermaid
flowchart TB
    Rewards[Monthly Rewards]
    Currency[Currency Rewards]
    Items[Item Rewards]
    Status[Status Rewards]
    
    Rewards --> Currency
    Rewards --> Items
    Rewards --> Status
    
    Currency --> CurrencyTypes["Regular currency
    Premium currency
    Special tokens"]
    
    Items --> ItemTypes["Unique equipment
    Special materials
    Exclusive skills"]
    
    Status --> StatusTypes["Titles
    Badges
    Rankings record"]
```

### Progression Tracking

1. **Character Progress**
   - Level progression
   - Gear advancement
   - Skill collection
   - Achievement points

2. **Combat Stats**
   - PvE completion rates
   - PvP win/loss ratio
   - Boss clear records
   - Ranking history

3. **Social Progress**
   - Guild contributions
   - Trading statistics
   - Faction reputation
   - Community involvement

4. **Economic Status**
   - Currency holdings
   - Market transactions
   - Material collections
   - Crafting success
