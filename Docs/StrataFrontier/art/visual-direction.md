# Approved visual direction

Accepted by the user on September 6, 2026. The [v2 concept gallery](hud-redesign-2026-09-06/README.md#refined-concept-gallery--v2) is the desired visual reference for Strata Frontier's environments, HUD, and pawn cards. The images establish a target; they do not certify implemented mechanics, finished assets, interaction behavior, or achievable performance.

## Environment and construction

Aim for attractive late-medieval low fantasy with convincing materials, atmospheric lighting, readable interiors, and visible human activity. The riverside camp, autumn village, and snowy settlement illustrate different places and stages in one continuous world.

Natural terrain should have organic slopes, irregular stream banks, rocks, soil, vegetation, and water. Avoid conspicuous voxel cubes or uniformly stepped, blocky ground as the normal wilderness appearance. The early stream concept is a positive reference for the desired landscape. Player-built walls should retain legible constituent material and construction detail.

The world is now specified at a requested 500 km × 500 km envelope with settlement possible in mountains and terrain that is actually diggable. The attractive stream imagery is not approval of an undiggable terrain foundation. The [world-scale and terrain review](../development/world-scale-terrain-review-2026-09-06.md) separates this hard capability requirement from the terrain-vendor evaluation.

The existing GDD already combines terrain quantization with smooth natural appearance. Accepted construction requirements now include **curved and diagonal walls**, wall-run/pattern authoring with individual-piece editing, and [every brick or stone remaining a persistent individual unit](../adr/0001-individual-masonry-pieces.md). Each piece supports individual placement, damage, removal, and repair. Every opening affects sight and projectiles; people pass only through sufficient clearance. Larger wall sections may group pieces while preserving their identities.

A mandatory axis-aligned grid-edge constraint is no longer the default wall-authoring rule. Arbitrary editable splines/freehand curves are required from the first implementation; a straight-runs-and-circular-arcs-only first tool was rejected. Cut/wedge masonry is allowed with persistent shape and material accounting. Terrain also uses freeform tools. Hidden cells are allowed, with no fixed resolution selected.

The accepted movement direction is [Unreal navmesh locally with separate world routing](../adr/0002-local-navmesh-and-world-routing.md), proven before migration. Fine geometry, snapping, floor/support joins, terrain representation, and rendering/physics parameters are future implementation proof work rather than unapproved replacements for the accepted design.

The straight shelters and local construction grid drawn in the v2 autumn image are illustrative. The approved images establish appearance and HUD direction; they do not override the later accepted freeform wall and terrain authoring requirements. Optional guides may assist placement, but a mandatory world-grid constraint is not part of the accepted authoring direction.

## People and HUD

### Visual approval workflow — September 7, 2026

For every visual task, consult this direction and the approved concepts before implementation. Use the [development testing resolution policy](../development/foundation.md#development-testing-resolution) for the preview and subsequent verification. Produce one clear preview at that resolution and the current UI/display scale, then pause for the user's explicit approval of the appearance. Do not repeat broad tests or commission broad reviews before that approval. Keep verification and progress updates focused; compile changed source and perform only the concise interaction needed to make the preview reviewable. Approval of an earlier concept does not approve the implemented preview.

The Build palette contains recipe **icons and names only**. Selecting a recipe displays its detailed card in the existing lower-left contextual inspector, the same area used for a selected pawn. Requirements, availability and prerequisite reasons, placement feedback, and execution/cancel controls belong there. Keep the underlying colonist or shelter identity intact, including the selected shelter used by sleeping-place planning. Bottom categories retain the concept's icon-above-label tiles, warm thin borders and selected accents.

Preserve the approved centered pawn cards and their visual quality: recognizable faces, names, coherent selection, and concise status cues. The current named group is Ada, Bram, Cora, Dain, and Esme. Growing populations require accessible overflow or filtering while retaining individual identity. The GDD's production intent is to render portraits from the actual character appearance; the generated portraits are visual references.

Use charcoal teal, ivory, and restrained ochre/brass accents. Keep the world central and use layered information:

- A thin top bar for settlement identity, time, weather when supported, pause, and speed.
- A transparent left resource rail with subtle backing, **Pinned / All** modes, chosen-resource pins, aligned counts, and scrolling when required.
- A contextual lower-left inspector, bottom action categories, actionable alerts at the upper right, and accessible map/roof/floor/overlay controls at the lower right.
- World labels for selection, hover, or a meaningful alert rather than every nearby object at once.

Do not show global sleeping-place or bed-capacity counters as permanent HUD information. Show relevant rest state through the person and environment. Floor sleeping alone is not a routine warning; a sustained inability to rest may warrant an actionable explanation. Removing a counter does not itself change the current prototype's sleeping rules.

Resource types and quantities shown in every v2 image are illustrative. Additional resources, food, temperature, multi-storey functions, and refined character/environment art are future work. The detailed brief records remaining consistency fixes, including stable resource-column order and reconciled key bindings.

## Relationship to existing work

The approved shelter v002 remains the verified starting kit and a useful scale reference. Its earlier acceptance does not imply that the grey prototype ground, mannequin, fixed whole-shelter recipe, or current left-sidebar HUD is the final visual target. Preserve those prototypes as evidence while planning the work toward this reference.

See the [plan and prototype review](../development/visual-target-plan-review-2026-09-06.md) for current facts, the settled design decisions, remaining technical proof, and the proposed gate sequence. The current request authorized documentation; no navigation or wall-system implementation has been performed.
