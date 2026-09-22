# Presentation, Interface, Audio, and Accessibility

## Visual direction

The target is readable stylized realism: modern lighting and materials, convincing modular architecture, clear interiors, expressive colonists, distinct silhouettes, and visible systemic state. Photorealism is not a goal.

Colonists use an extensible humanoid rig with modular bodies, faces, hair, clothing, armor, equipment, cultural detail, age variation, and visible major injury. Portraits render from the same 3D character rather than separate portrait assets. Future species remain possible through composition, but the initial population is human.

## Camera

The strategy camera rotates freely, adjusts pitch, and zooms from close character inspection to regional overview. It supports rapid travel between remote selected colonists, vertical cut planes, roof hiding, wall fading, floor isolation, and exploded storeys.

When focusing a distant colonist, the game streams and promotes the destination while using a strategic zoom transition. It holds at overview rather than showing incomplete terrain. High-level orders can be queued remotely; exact placement requires promotion.

## Animation

Authored locomotion and core action clips combine with procedural foot placement, hand targets, gaze, equipment alignment, and workstation interaction points. Simulation decides outcomes; animation communicates them. Full motion matching and bespoke animation for every recipe are outside early scope.

## Interface philosophy

The interface is dense but layered for PC play:

- Searchable lists and sortable tables
- Work and policy matrices
- Pinned inspectors and comparison tooltips
- Saved filters and configurable columns
- Keyboard shortcuts and searchable commands
- Contextual links to a searchable encyclopedia

The default workspace is stable and readable, with resizable panels, detachable large management views, pinned inspectors, and per-resolution persistence. A fully general editor-style docking environment is not required.

Controls follow familiar colony-sim conventions: left-click selection, right-click contextual orders, drag selection, queued orders with modifiers, number groups, pause and speed keys, construction modes, and full rebinding.

## Overlays

World overlays cover construction grid, storeys, support, rooms, temperature, ventilation, smoke, light, water, groundwater, fertility, moisture, crops, resources, ownership, work areas, storage, traffic, navigation, cover, range, faction influence, communication, fire risk, and simulation fidelity. Presets prevent overload while advanced users can compose views.

## Sound

Audio is atmospheric and informative: tools, work, machinery, weather, animals, structures, combat, water, and settlement activity respond to distance and enclosure. Character vocalization is restrained and avoids repetitive spoken barks. Alerts use recognizable nonverbal cues with visual equivalents.

Music is adaptive but sparse, leaving substantial space for ambient sound. Instrumentation responds to culture, season, settlement condition, exploration, tension, and Echo activity. Combat music grows from world tension rather than switching instantly to a generic battle track.

## Accessibility

Foundational requirements include:

- Complete key rebinding
- Scalable text and UI
- Colorblind-safe palettes and pattern alternatives
- Reduced motion and flashing
- Subtitles and sound-event visualization
- Adjustable camera movement
- Readable fonts
- Pause-on-event policies
- Control over combat speed
- Unicode, font fallback, plural-aware text, and pseudo-localization support

Actual translation and polished onboarding are late-production work. Architecture support begins early.

## Onboarding

Near release, onboarding should combine an optional interactive tutorial, a guided systemic opening scenario, contextual prompts, and a linked encyclopedia. Early prototypes prioritize diagnostic tools rather than polished tutorials.
