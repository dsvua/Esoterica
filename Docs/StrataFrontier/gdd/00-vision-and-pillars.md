# Vision, Audience, and Pillars

## Product statement

Strata Frontier is a premium single-player PC colony simulation in which the player guides a small, character-driven frontier community through survival, construction, exploration, conflict, and generational change in one persistent procedurally generated 3D world.

The player does not move between disposable level maps. Colonists, settlements, camps, caravans, ruins, factions, weather, ecology, and historical consequences occupy the same continuous world.

## Creative north star

> Lead a vulnerable frontier community that builds a permanent home, explores a dangerous land, and creates memorable stories through simulation.

When systems compete for attention, use this priority order:

1. Character management and emergent stories
2. Building and settlement design
3. Production, logistics, and economy
4. Exploration of the open world
5. Tactical combat
6. Diplomacy and faction politics
7. Technology and supernatural progression

## Reference contract

- **RimWorld** is the primary gameplay reference: autonomous pawns, work priorities, immediate contextual orders, drafting, readable research, and incident-paced emergent stories.
- **Going Medieval** is a presentation and construction reference: attractive 3D settlements, visible interiors, vertical building, and structural legibility. Its gameplay pacing is not the target.
- **Dwarf Fortress** is a selective depth and generation reference: varied landforms, histories, aquifers, materiality, and long consequence chains. Its interface, graphical presentation, pure indirect control, and exhaustive simulation are not targets.
- **Combat Extended** informs the physical attack-to-wound model, especially hard armor/penetration relationships. Its code, tuning, UI, and exact content are not copied.
- **Voxel Plugin** informs demand-driven hybrid height/volume terrain, bounded edits, and derived caches. It is not a runtime dependency or authoritative data model.

## Pillars

### People before population

Every colonist is named, inspectable, socially connected, and directly commandable. Even at the intended soft maximum, people must not collapse into anonymous population counters.

### One world, no colony maps

The world is internally partitioned for streaming, navigation, physics, saves, and simulation LOD, but those partitions are not separate gameplay levels. A strategic view represents the same physical space.

### Build anywhere, remember everything meaningful

Players may settle, dig, construct, abandon, return, or rebuild anywhere. Terrain edits, buildings, graves, ruins, discoveries, and important ecological changes persist.

### Explainable systemic outcomes

Combat, health, mood, logistics, construction, diplomacy, disasters, and supernatural events must expose causes. Randomness creates variation, not unexplained rule breaking.

### Depth through connected systems

Water connects geology, wells, sanitation, farming, mining, transport, power, defense, and disasters. Materials connect extraction, hauling, construction, comfort, trade, and combat. A system is justified by the decisions it creates across the game.

### Source-visible, data-oriented implementation

The project is designed for a solo developer using AI code assistants. Authoritative data stays in testable C++ and human-readable content sources, separate from binary presentation scenes.

## Audience and difficulty

The primary audience is experienced colony-simulation players. Layered interfaces, contextual teaching, searchable documentation, and explicit causality should make the game learnable by broader strategy players.

Default difficulty produces serious setbacks and recovery stories rather than frequent arbitrary campaign termination. Presets expose independent controls for hostile pressure, resources, agriculture, disease, injury, mood, weather, disasters, and the Echo. Difficulty may change mid-campaign and is recorded in history without shaming the player.

## Player role

The player is an unseen management authority, not an embodied leader, deity, or possessed character. Colonists may create leaders and institutions, but no privileged avatar determines continuity. The campaign is lost only when every playable community member is dead.

## Tone and content

The setting is original late-medieval low fantasy with stylized realism and rare but real supernatural forces. Permanent death, injury, illness, substance use, fictional beliefs, war, and morally difficult survival decisions may occur.

The core game excludes sexual violence, slavery, forced prisoner labor, and torture. Childhood exists but is presented responsibly and without exploitative imagery.
