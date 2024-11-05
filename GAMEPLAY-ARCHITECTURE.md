# Kyva Online - Gameplay Architecture

## Overview
The gameplay architecture consists of three main components working together:
- React (UI & Game Controller)
- Backend (.NET - Game Logic)
- Godot (3D Visualization)

## Core Architecture

```mermaid
flowchart TB
    subgraph "Client Browser"
        subgraph "React Layer"
            RC[React Controller]
            UI[Game UI]
            GC[Godot Communication]
        end
        
        subgraph "Godot Layer"
            GL[Godot Instance]
            VFX[Visual Effects]
            Anim[Animation System]
            Model[3D Models]
        end
    end
    
    subgraph "Server"
        BE[Backend Logic]
        DB[(Game Database)]
    end
    
    %% React internal communication
    RC --> UI
    RC --> GC
    
    %% React-Backend communication
    RC <--> BE
    BE <--> DB
    
    %% React-Godot communication
    GC <--> GL
    GL --> VFX
    GL --> Anim
    GL --> Model
```

## Combat Flow Architecture

```mermaid
sequenceDiagram
    participant UI as Game UI
    participant RC as React Controller
    participant BE as Backend
    participant GD as Godot

    Note over UI,GD: Combat Initialization
    UI->>RC: Player Action Selected
    RC->>BE: Validate Action
    BE->>BE: Process Game Logic
    BE->>RC: Return Action Result
    
    alt Action Valid
        RC->>GD: Play Animation Command
        GD->>GD: Process Animation
        GD->>RC: Animation Complete
        RC->>UI: Update Game State
    else Action Invalid
        RC->>UI: Show Error
    end
```

## Detailed Component Communication

### React Controller Functions
```mermaid
flowchart TB
    RC[React Controller]
    
    RC --> GameState[Game State Management]
    RC --> ActionHandler[Action Processing]
    RC --> GodotBridge[Godot Communication]
    
    GameState --> StateFeatures["Combat state
    Player stats
    UI updates"]
    
    ActionHandler --> ActionFeatures["Validate moves
    Process responses
    Handle animations"]
    
    GodotBridge --> BridgeFeatures["Animation triggers
    Model updates
    Scene control"]
```

### Combat System Architecture

```mermaid
flowchart TB
    Combat[Combat System]
    
    Combat --> Init[Initialize Combat]
    Combat --> Process[Process Actions]
    Combat --> Resolve[Resolve Combat]
    
    Init --> InitSteps["Load combat data
    Set initial states
    Prepare scenes"]
    
    Process --> ProcessSteps["Validate actions
    Calculate results
    Trigger animations"]
    
    Resolve --> ResolveSteps["Update states
    Save results
    Clean up"]
```

## PvP Architecture

```mermaid
sequenceDiagram
    participant P1 as Player 1 UI
    participant RC as React Controller
    participant BE as Backend
    participant GD as Godot
    participant P2 as Player 2 UI

    Note over P1,P2: Ranked Battle Flow
    P1->>RC: Select Action
    RC->>BE: Validate Turn
    BE->>BE: Process Turn
    BE->>RC: Return Results
    RC->>GD: Animate Action
    GD->>RC: Animation Complete
    RC->>P1: Update P1 UI
    RC->>P2: Update P2 UI
```

## Gameplay Data Flow

```mermaid
flowchart LR
    UI[Game UI]
    RC[React Controller]
    BE[Backend]
    GD[Godot]
    
    UI -->|User Input| RC
    RC -->|Action Request| BE
    BE -->|Validation Result| RC
    RC -->|Animation Command| GD
    GD -->|Completion Signal| RC
    RC -->|State Update| UI
```

## Component Responsibilities

### React Controller
- Manages game state
- Processes user inputs
- Communicates with backend
- Controls Godot instance
- Updates UI

### Backend
- Validates all actions
- Processes game logic
- Maintains game state
- Manages player data
- Handles combat calculations

### Godot Instance
- Renders 3D scenes
- Plays animations
- Handles visual effects
- Manages model states
- Reports completion status

## State Management

```mermaid
flowchart TB
    State[Game State]
    
    State --> Combat[Combat State]
    State --> Player[Player State]
    State --> Scene[Scene State]
    
    Combat --> CombatData["Active skills
    Turn order
    Action queue"]
    
    Player --> PlayerData["Current stats
    Equipment
    Status effects"]
    
    Scene --> SceneData["Animation states
    Visual effects
    Model positions"]
```

## Error Handling

```mermaid
flowchart TB
    Error[Error Handling]
    
    Error --> Network[Network Errors]
    Error --> Game[Game Logic Errors]
    Error --> Visual[Visual Errors]
    
    Network --> NetworkHandle["Connection retry
    State recovery
    User notification"]
    
    Game --> GameHandle["Action validation
    State rollback
    Error messages"]
    
    Visual --> VisualHandle["Animation reset
    Scene recovery
    Visual feedback"]
```
