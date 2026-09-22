# Construction, Terrain, and Settlements

## Construction grid

Construction uses a one-meter square planning grid:

- Floors occupy cells.
- Walls and doors occupy cell edges.
- Pillars occupy vertices.
- Furniture uses cell footprints plus explicit interaction and clearance positions.
- Standard storeys are approximately three meters high.

Edge walls preserve believable interior space. Navigation treats floor cells as nodes and walls or doors as connections between nodes. Furniture may snap to wall-edge anchors, so wall-adjacent placement is predictable rather than a pathfinding exception.

## Building workflow

Players place ghost blueprints. Colonists deliver physical materials and perform construction work. Plans can be prioritized, suspended, copied, cancelled, mirrored, rotated, or replaced in place. Unfinished structures occupy space according to construction stage.

Planning tools include:

- Line, rectangle, room-outline, and flood-fill placement
- Repeated spacing and material substitution
- Copy/paste and reusable blueprints
- Multi-storey previews and vertical cut planes
- Planning-only layers
- Priority painting and suspension
- Material, labor, access, and support previews

Construction skill affects speed, waste risk, durability, beauty, and furniture quality without making structural dimensions unpredictable.

## Rooms and visibility

Connected-volume analysis detects enclosure and supports temperature, ventilation, smoke, daylight, rain exposure, and room function. Room use is inferred from furniture, storage, cleanliness, access, and activity; players may assign ownership and allowed uses. One hall may contain several activity zones.

The camera supports selectable cut planes, floor isolation, roof hiding, wall fading, and an optional exploded-storey view.

## Terrain editing

Authoritative excavation and filling use quantized one-meter cells and material state. Natural terrain renders with smooth organic surfaces. Explicit smoothing, finishing, terracing, and room-excavation tools create grid-compatible floors and faces for construction and furniture.

Players may designate volumes, rooms, tunnels, stairs, shafts, vein following, smoothing, reinforcement, filling, drainage, and protected access. Every removed cell yields physical material based on geology, tools, skill, and breakage.

## Structural integrity

Foundations, terrain, walls, pillars, beams, and arches form a readable support graph. Materials contribute weight and strength classes. Unsupported excavation and construction can collapse.

Planning overlays show support paths, margins, predicted overload, and dependent elements before work begins. Structural depth should create engineering choices without requiring external calculation tools.

## Materials

Wood, earth, brick, stone, metal, glass, cloth, and supernatural materials differ through useful properties:

- Strength and weight
- Insulation and thermal mass
- Fire and water resistance
- Rot and weathering
- Workability and labor cost
- Beauty and cultural meaning
- Maintenance and value

Materials visibly affect finished structures and matter to comfort, survival, production, trade, or defense.

## Roofs, utilities, and atmosphere

Roofs require support and use material-appropriate spans and slopes. Connected rooms simulate temperature, ventilation, smoke, daylight, weather exposure, and precipitation through coarse volumes rather than full fluid dynamics.

Pre-industrial utility systems include water supply, cisterns, drainage, sanitation, irrigation, ventilation, heating, fuel, lighting, and mechanical power. Wells, channels, pipes, hearths, chimneys, latrines, waterwheels, windmills, shafts, belts, and gears connect physically. Electricity is outside the initial technology ceiling.

## Maintenance and demolition

Structures lose condition through weather, use, impact, fire, rot, water, and inadequate support—not universal passive decay. Standing policies automate maintenance. Safe deconstruction follows dependency order, previews collapse risk, and salvages material according to condition, tools, material, and skill.

## Sites without maps

A site is an optional management anchor and influence area, not a level boundary. It groups population lists, alerts, storage, work, schedules, defense, and statistics. Sites may overlap, merge, split, move, or disappear while physical structures remain.

All sites obey identical rules. The preferred campaign shape is one principal settlement supported by camps and expeditions, but no artificial site count limit exists.

## Fortification and siege

Players may construct walls, towers, gates, ditches, traps, battlements, fortified underground routes, and protected utilities. Attackers use technology and knowledge to choose ladders, rams, siege engines, fire, tunneling, blockade, starvation, or naval landing. Siege behavior uses ordinary construction, physics, logistics, morale, and combat rules.
