# Asset audition result — 2026-09-04

The original shelter v002 is the **approved starting visual baseline**. On 2026-09-04, the user confirmed its style and level of detail: “yes, I like it so far.” This approval establishes the starting art direction; the reimport, collision, animation and performance limitations below still apply. The marketplace crate and trees remain adaptation candidates without production approval. Open `/Game/StrataFrontier/Tests/Art/L_AssetAudition`; the saved presentation has the roof visible, door closed and mannequin outside.

## Decisions

| Set | Observed cost | Decision |
| --- | --- | --- |
| Original shelter v002 | 9 meshes, 61 placed pieces, 69,204 placed triangles, 5 materials, 4 base-color textures; 1 LOD per mesh | Approved starting visual baseline for style and detail. Reuse as the starting kit with the documented native import repair and remaining technical checks. |
| Crate | 3 meshes, 3,998 triangles; three 2048² source textures | Adapt/reuse candidate. Readable boards and iron, but more surface detail than the shelter. Simplify collision/texture budget when promoted. |
| Dungeon door | 5 meshes, 1,591 triangles; three 4096² source textures | Keep as a reference; use the original shelter door. At 0.62 scale its ornate frame is about 299 cm tall, but leaf only 186 cm. It does not match the shelter's clear opening/proportions. |
| Stylized broadleaf | 5 meshes, 24,863 triangles; one 2048² source texture | Adapt or replace. Readable crown and shadow, but strong green saturation, flat trunk color and high geometry cost for repeated vegetation. |
| Low-poly conifer (first variant) | 2 meshes, 451 triangles; pack has three 1024² bark textures and two 2048² leaf textures | Adapt candidate. Fine crown/needle silhouette; translucent leaf import gives weak/missing crown shadow and potential overdraw cost. |
| Existing Manny | SKM_Manny_Simple, SK_Mannequin skeleton, 161 bones | Temporary scale/animation reference. Original colonist and work clips are still future art work. |

Candidate counts are queried Unreal render LOD0/fallback values, not full Nanite source geometry. In particular, the broadleaf uses reduced fallback geometry; its full Nanite source is larger than the table value. Shelter counts are the authored non-Nanite mesh triangles. None of the static meshes has additional LODs. Geometry counts do not establish GPU cost. Only Object_4 + Object_5 of the three-variant low-poly tree pack are placed. Both tree candidates are normalized to 500 cm height and compared at equal depth/distance. No tree modeling or material overhaul was performed.

## Verified results

- Correct centimeter bounds on all nine shelter meshes; 100 cm floor/grid step, 300 cm wall/storey, 400 × 400 cm structural footprint. The 14 roof/gable/ridge actors can be hidden for inspection. Close, overview and roof-off views show joins and usable floor.
- Original doorway has a 116 × 240 cm opening. Separate leaf pivot is the authored hinge at world (-243, -7.2, 22) cm; its bottom clears the finished floor at Z18 by 4 cm. Closed yaw180° and open yaw270° were inspected, then closed restored.
- Door geometry rays from Y-80 to Y80: center X-300/Z140 hits at 74 cm when closed and returns no hit when open; both jambs and header block. Crate ray hits at 78.864 cm; its three imported parts each contain one convex hull. These are shape and ray checks, **not capsule movement, navigation, or runtime interaction tests**.
- Native FBX import replaced UBX boxes with generated hulls, including an incorrectly solid doorway. Repaired seven meshes to 12 authored boxes; retained the two authored UCX hulls on roof/gable. Reopened map confirms the counts. Exact centimeter recipe: [native-import-repair.json](../../SourceArt/Environment/Architecture/FrontierShelter_Audition/v002/exports/native-import-repair.json).
- Native FBX import omitted roughness/metallic constants. Added constant material inputs using the source values: timber 0.78/0, plaster 0.90/0, stone 0.87/0, roof 0.78/0, iron 0.43/0.72. Four base-color textures remain connected; no normal maps were authored for this kit.
- Simulate playback visibly exercised `/Game/Characters/Mannequins/Anims/Unarmed/MM_Idle`, `Unarmed/Walk/MF_Unarmed_Walk_Fwd` and `Unarmed/Attack/MM_Attack_01`. No obvious skeletal collapse observed. These are idle/walk/combat reference clips, not hauling/construction animations. Stills do not establish loop continuity or foot sliding. Final outside mannequin is at Z0; the interior check placed it on the Z18 floor. Early animation stills used the floor-reference Z18 outside and are pose evidence, not foot-contact evidence.
- Saved only the audition assets and reopened the map: 94 actors, all 14 roof components visible, closed leaf at the authored transform, mannequin at (-200,-70,0), PIE stopped. The original startup map and pre-existing assets remain intact.
- Independent visual review accepted close/character, equal-scale vegetation and corrected interior evidence. Adaptation issues remain listed above.

The conifer leaf material instance uses `/InterchangeAssets/gltf/Substrate/M_GLTF`, two-sided `BLEND_TranslucentColoredTransmittance`, and no cast-dynamic-shadow-as-masked override. Component cast-shadow flags are enabled. Correct the foliage alpha/shadow treatment before production use; this audition keeps the imported candidate visible for comparison.

## Real editor evidence

All PNGs below are native Unreal HighResShot captures at 1920 × 1080. FOV90°, perspective/lit viewport, Development Editor UE5.8 CL56702186, DirectX12. Camera values are centimeters/degrees (pitch, yaw, roll).

| File | Camera location | Rotation | State |
| --- | --- | --- | --- |
| [Overview](evidence/asset-audition/overview.png) | -950,-1150,1000 | -33,55,0 | Final saved presentation after reopen |
| [Doorway/crate/idle](evidence/asset-audition/doorway-crate-idle.png) | -580,-540,360 | -20,62,0 | Simulate idle reference |
| [Walk](evidence/asset-audition/character-walk.png) | same | same | Simulate walk reference |
| [Action](evidence/asset-audition/character-action.png) | same | same | Simulate attack reference |
| [Roof-off interior](evidence/asset-audition/interior-roof-off.png) | -400,-100,850 | -68,70,0 | 14 roof components hidden, door open, mannequin inside; restored afterward |
| [Equal-scale trees](evidence/asset-audition/vegetation-equal-scale.png) | 535,-120,420 | -10,90,0 | Both 500 cm tall, Y650 |

Map-local lighting: sun100,000 lux,6500K, pitch-45°/yaw120°, source angle1.5°; movable realtime SkyLight intensity1; fixed EV14 exposure, bias0, motion blur0. One map-local downward RectLight at (-300,200,295),400,000 lumens,250 × 250 cm,450 cm radius, no shadows provides interior review fill. This is an audition lighting aid, not an implemented building lighting system. Template sky/atmosphere/fog/cloud actors remain. Rendering history was warmed through repeated native viewport draws before accepting captures.

Hardware: Intel i9-10900KF, RTX3080, Windows11. Quality groups were level3. [Editor frame sample](evidence/asset-audition/editor-frame-sample.txt):99 frames/33 seconds,3FPS average, nominal333ms wall-frame interval; reported game154.15ms/render1.72ms/GPU0.20ms. **This was a background-throttled editor sample**, with idle included, not a valid runtime benchmark. Its WindowsEditor metadata reports2560 × 1440 desktop resolution; evidence PNGs are1920 × 1080. It neither passes nor fails the1080p/60 or50-colonist goals. Profiling overdraw and representative gameplay performance remains future work.

## Changed files and pipeline notes

- New map: `Content/StrataFrontier/Tests/Art/L_AssetAudition.umap`.
- New kit: nine `SM_SF_Shelter_*`, five `M_SF_Shelter_*`, four `T_SF_Shelter_*_BaseColor` assets under `Content/StrataFrontier/Art/Environment/Architecture/FrontierShelter_Audition/`.
- Four isolated imported candidate subfolders under `Content/StrataFrontier/Tests/Art/Candidates/{Crate,Door,TreeStylized,TreesLowPoly}/scene/`. Exact paths, bounds, LOD counts, cameras and persistence values are in [verification.json](evidence/asset-audition/verification.json).
- Editable source, reproducible Blender scripts, exports, native repair recipe and validation: [source handoff](../../SourceArt/Environment/Architecture/FrontierShelter_Audition/README.md). v002 is the accepted import revision; v001 and the unaccepted UCX probe are optional ignored diagnostic history under Saved/AssetAudition/SourceDiagnostics/FrontierShelter_Audition, excluded from the checkpoint.
- `Config/DefaultEngine.ini.template` and ignored local `DefaultEngine.ini`: `r.EyeAdaptation.CachedLightingPreExposure=8`, required to put fixed EV14 within the cached-lighting range and remove the exposure warning. No private MCP token enters tracked config.
- `Config/DefaultGame.ini`: canonical GameFeatureData primary-asset scan entry. A startup-only ImportAssets `-help` commandlet returned exit0 with0errors/0warnings after the fix, with no import/save operation. Earlier commandlet imports succeeded but returned exit1 due the pre-existing GameFeatureData registration error.
- Bundled candidate author/license records and source fingerprints are retained in [asset-manifest.json](asset-manifest.json) and [credits](evidence/asset-audition/credits/). The external source library was not modified.

No C++ gameplay or Blueprint logic was added. There is no colony loop, runtime door controller, pathfinding validation, work animation, save/load gameplay or performance approval in this milestone. The shelter's visual baseline is approved; gameplay implementation remains a following milestone.
