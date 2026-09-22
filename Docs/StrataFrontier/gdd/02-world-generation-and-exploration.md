# World Generation and Exploration

## World promise

Each campaign creates one continuous procedurally generated world whose coastline may form a single large island, an archipelago, or anything between. Ocean provides a natural outer boundary. The default major landmass should take roughly two to five in-game travel days to cross under favorable conditions; compact and larger presets are supported.

The experience is seamless even though implementation uses hidden cells, chunks, regions, physics bubbles, navigation sectors, and simulation tiers. Ordinary travel has no level-transition screen. Strategic overview, camera travel, and accelerated time all observe the same world.

## Generation pipeline

World generation is hierarchical:

1. Seed and configuration
2. Coarse elevation, coastline, watersheds, rivers, ocean, and island topology
3. Climate, seasons, soils, biomes, groundwater, geology, and resources
4. Cultures, populations, settlements, roads, routes, and territorial influence
5. Coarse early history followed by more detailed recent history
6. Scenario placement and starting knowledge
7. Deterministic high-resolution terrain materialization when regions are approached

Untouched high-resolution terrain can be reproduced from seed. Saves store edits and nonprocedural state, not generated render meshes.

## History

Default prehistory spans approximately 100–300 years. Early periods coarsely resolve cultures, migrations, settlement foundations, disasters, and major conflicts. Recent decades track named leaders, important families, artifacts, wars, routes, ruins, and claims more closely.

History produces gameplay evidence: occupied and abandoned settlements, borders, roads, graves, ruins, relationships, trade patterns, damaged structures, disputed claims, relics, and Echo concentrations. It does not attempt Dwarf Fortress-level person simulation across every historical year.

## Cultures, factions, and settlement density

Default worlds are wilderness-dominant, with roughly three to six broad cultures and six to twelve active factions. World presets may be emptier or politically crowded.

Cultures are assembled from authored building blocks—values, institutions, aesthetics, law, naming, technology, belief, and economic tendencies. A culture can contain several allied or rival factions. Generated architecture varies in road patterns, rooms, public spaces, defenses, materials, roofs, decoration, storage, sanitation, and institutions while obeying common construction rules.

NPC settlements physically exist. Terrain-aware procedural grammars create valid villages, forts, towns, camps, and infrastructure; historical simulation expands, damages, repairs, abandons, or repurposes them. When an aggregate distant settlement becomes detailed, population, households, professions, wealth, defenses, institutions, resources, damage, culture, and important people constrain the result.

## Geography, climate, and ecology

Each world has a coherent regional climate with variation driven by elevation, drainage, soils, rain shadows, latitude-like gradients, and ocean exposure. A typical world contains five to eight connected biomes rather than every possible biome.

Regional fronts produce rain, snow, fog, wind, heat, cold, lightning, and storms. Weather affects visibility, projectiles, travel, fire, crops, groundwater recharge, flooding, comfort, disease, sailing, and power generation.

Surface state includes wetness, mud, snow depth, ice, tracks, and maintenance. Colonists may drain, pave, shovel, plow, salt, bridge, and maintain routes.

Forests regrow; wildlife migrates and reproduces; soil and fisheries may recover. Ore and exceptional stone are finite. Overharvesting, fire, contamination, erosion, and Echo disturbance persist, while stewardship can restore renewable systems.

## Geology and subsurface

Worlds contain stylized coherent soil, weathered layers, bedrock strata, intrusions, folds, faults, ore bodies, aquifers, caves, fossils, and Echo-bearing deposits. Geology affects water, construction materials, stability, mining method, settlement placement, and exploration.

Aquifers are locally finite but regionally renewed by rainfall, surface water, and subsurface flow. Player-facing light aquifers seep slowly; heavy formations can rapidly flood excavations. Groundwater is addressed in detail in the [construction and environment implementation](../implementation/05-construction-hydrology-environment.md).

## Knowledge and discovery

Explored geography remains known, but changing facts become stale. Enemy movement, prices, hazards, settlement condition, and resource information require observation or reports. Owned colonists remain selectable for usability; isolated information may be marked delayed.

Cartography is collective knowledge. Explorers reveal rough data, surveyors improve it, and maps can be created, copied, lost, traded, stolen, and updated. Surface geology, plants, water, ruins, local testimony, and old workings hint at underground resources. Prospecting, pits, drilling, experts, and later instruments refine confidence. Deposits exist from world generation and are never spawned as a reward for searching.

## Exploration and persistence

Terrain changes, buildings, sites, colonists, graves, important objects, discoveries, ruins, and meaningful ecological effects persist. Minor debris, footprints, stains, and irrelevant abandoned items may decay under explicit rules. Untouched procedural details can rematerialize from seed.

Abandoned sites weather, collapse, burn, flood, overgrow, get salvaged, attract occupants, or accumulate historical and Echo significance. Players can return, reclaim, repair, excavate, or repurpose them.

## Biota and agriculture envelope

The initial crop target is a compact authored set of roughly 12–20 meaningful crops across grain, legume, root, vegetable, fruit, fiber, oil, fodder, herb, and cultural roles. Local varieties modify tolerance, yield, season, disease resistance, and quality without a full genetics simulator.

Domestic animals cover meat, milk, eggs, fiber, hides, riding, packing, draft power, guarding, companionship, and pest control. A small set of visible inherited traits supports selective breeding. Nearby animals are individual agents; distant wildlife uses population cohorts.
