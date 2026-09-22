# First asset audition

Status: implemented and visually reviewed on 2026-09-04. See [verified result and evidence](asset-audition-result.md). No production asset has been approved. The source library is read-only at `C:\Users\sdanc\OneDrive\Documents\Backup\Assets` on the current workstation. Candidate paths in `asset-manifest.json` are relative to that root.

## Purpose and boundary

Choose a consistent, readable starting art set for the [visual direction](../gdd/08-presentation-ui-audio-accessibility.md) and [construction grid](../gdd/04-construction-terrain-and-settlements.md). The result is one small reviewable scene, not the colony simulation. No purchases, broad vendor imports, engine upgrades, or changes to the startup map are part of this milestone.

Planned level: `/Game/StrataFrontier/Tests/Art/L_AssetAudition`. Reusable accepted assets belong under `/Game/StrataFrontier/Art/`. Trial imports go under `/Game/StrataFrontier/Tests/Art/Candidates/`, separated by source candidate so rejected trials cannot silently become production dependencies.

## Scene contents

- One custom 4 m by 4 m shelter assembled from a 1 m grid kit, with an approximately 3 m storey, doorway, and removable roof pieces. Created as v002 and verified in Unreal; see the SourceArt handoff below.
- `models/dungeon_door/scene.gltf`: doorway candidate with separate door/frame/handle nodes. Imported and visually reviewed; its frame/leaf proportions favor using the original shelter door. See the result for geometry checks and limits. No supplied animation was found.
- `models/box_stylized/scene.gltf`: crate/stockpile candidate with wood and metal parts. Imported and visually reviewed at88.25cm height; collision shapes and a ray hit are verified. Simplification/style adaptations remain listed in the result.
- Both `models/stylized_tree/scene.gltf` and `models/low_poly_trees_free/scene.gltf`: side-by-side vegetation candidates. Compared silhouette and material response at equal height/distance; queried render/fallback geometry counts and production limits are in the result. Overdraw remains unprofiled. Names alone do not establish optimization or style fit.
- One original simple colonist placeholder is preferred; the user authorized original replacement assets on 2026-09-04. `models/King.gltf` has a skin and 24 named clips, including idle, walk, run, interact, and sword actions, but its source is unknown. The loose Palladin/Vanguard FBXs and action clips also have unknown provenance. The user does not remember their sources and plans to replace them; keep them as temporary references, not dependencies of the new art set. Use the existing project mannequin for scale and checks until the original placeholder is available; do not call it a finished colonist.
- Optional brick-material swatch from `Materials/seamless_pbr_texture_brick_05/`; it is a surface trial, not evidence of a modular building kit.

Several shortlisted environment/material sources include author/source/CC-BY-4.0 metadata and local credit files. Preserve those records. The user confirmed that the character sources are unknown and replacement is planned. No further provenance search is required for this milestone because original art is the chosen production path; the manifest retains their temporary-reference status.

The scanned folder and ZIP member names did not reveal a medieval modular building kit, `.blend` source, or Unreal asset package. Existing project AppleTree sources are separate pre-existing work and must be preserved; their quality has not been re-reviewed here.

## Source and export contract

Custom kit source: `SourceArt/Environment/Architecture/FrontierShelter_Audition/`.

Planned accepted Unreal kit destination: `/Game/StrataFrontier/Art/Environment/Architecture/FrontierShelter_Audition/`.

Keep the editable `.blend`, reproducible construction/export notes or script, selected export files, and validation evidence together. The detailed handoff is `SourceArt/Environment/Architecture/FrontierShelter_Audition/README.md`. Do not overwrite vendor originals. Record actual import settings and any adaptation in the manifest after inspection; the tested v002 FBX path and required native repair are now recorded in the result and source handoff.

## Execution order

1. Confirm that the intended project is open and discover Epic MCP toolsets and any applicable editor-registered guidance. Record active level, selection, unsaved changes, compilation state, and PIE state before changes.
2. Establish a source-control checkpoint; keep unrelated assets and default maps intact.
3. Inspect candidate source dependencies and provenance. Import only the selected trial set; resolve texture assignment, scale, axes, materials, and collision individually.
4. Create the custom shelter through the Blender specialist when its connection is available; verify the editable source and exports before Unreal integration.
5. Assemble the audition level. Use level-local lighting and camera setup. Keep any interaction implementation in C++; no new Blueprint logic is authorized by convenience alone.
6. Save only newly created or deliberately changed audition assets. Reopen the level to verify persistence. Compile and playtest only when changed C++ or requested interactions require it.
7. Capture real editor evidence, record adaptation decisions, and produce a reviewed checkpoint. Do not start the larger colony loop until this result can be reviewed.

## Acceptance and visual evidence

The table below is the acceptance specification. Completed checks and explicit limits are recorded in [the result](asset-audition-result.md). Store captures under `docs/art/evidence/asset-audition/` when actual evidence exists. Record map revision, camera transform, resolution, rendering quality, lighting/time, viewport mode, and hardware with each capture set.

| Check | Required evidence |
| --- | --- |
| Import integrity | Selected meshes/textures/materials present; no missing dependencies or relevant import errors |
| Modular construction | 1 m placements, shared boundaries, corner joins, roof joints, and approximately 3 m storey verified numerically and visually |
| Interaction geometry | Door/frame separation, hinge, floor clearance, doorway passage, crate collision, and shelter access verified |
| Character | Original placeholder or existing project mannequin identified; skeleton inspected; idle/walk/action clips observed where available; foot contact, orientation, scale, and any missing clips recorded |
| Visual consistency | Close-up and gameplay-distance views compare palette, roughness, proportions, silhouette, and legibility across reused and custom assets |
| Interior readability | Roof removed and interior views show usable space without gaps, clipping, or obscured important objects |
| Vegetation | Both candidates inspected at matching distances with observed geometry/material/texture costs; do not infer runtime cost from file names |
| Performance context | Record an observed frame-time sample and hardware/settings; this tiny scene cannot validate the GDD's 50-colonist performance target |
| Persistence | Audition level reopens with the expected assets and placements |
| Handoff | Real screenshots plus reuse/adapt/replace decisions, named changed assets, outstanding issues, and a reviewed Git checkpoint |

Suggested evidence views: full scene at strategy distance; close doorway and crate; both tree silhouettes at equal scale; character beside the doorway; roof-off interior. Add a short motion recording for the character and any implemented door behavior. A source render cannot replace the Unreal visual check.

## Following milestone

After the audition checkpoint, build a C++ slice with 5-8 colonists gathering material, reserving it, hauling it, constructing one shelter, and preserving the result through save/load. Check interruptions, direct orders, unavailable materials, blocked access, and pause/speed behavior. This is future scope, not implemented by the asset audition.
