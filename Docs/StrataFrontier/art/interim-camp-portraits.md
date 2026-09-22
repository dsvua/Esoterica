# Interim camp portraits

Ticket 02 uses the five faces from the user-approved [first-night v2 concept](hud-redesign-2026-09-06/01-first-night-v2.png), generated with the built-in imagegen tool. Its [generation record](hud-redesign-2026-09-06/PROMPTS-v2.md) and [approved direction](visual-direction.md) remain authoritative. These are interim UI illustrations. The playable mannequin appearance is unchanged; later production portraits still need to derive from actual character appearance.

`/Game/StrataFrontier/UI/Portraits/T_CampPortraitConcept` imports that unchanged 1672 × 941 source image. The native UI samples only the face rectangles below. Concept names, badges, need bars, resource quantities and world artwork are excluded from every portrait brush. All labels and observations are rendered live in C++ UMG.

| Saved colonist ID | Identity | Source rectangle, pixels (left, top, width, height) |
| --- | --- | --- |
| 1 | Ada | 574, 64, 84, 94 |
| 2 | Bram | 683, 64, 84, 94 |
| 3 | Cora | 795, 64, 84, 94 |
| 4 | Dain | 905, 64, 84, 94 |
| 5 | Esme | 1017, 64, 84, 94 |

`SFCampPortraits::Brush` keys this mapping by saved identity, independently of roster order. Unmapped IDs or unavailable art retain an initial and the live full name on the card, with normal selection and inspection. The inspector always retains the name. The single texture uses the UI texture group, uncompressed UI color, sRGB, no mipmaps and no streaming. A native class-default reference includes it in asset cooking; the concept PNG is not read from the documentation directory at runtime.

The source rectangle is intentionally modest in resolution. Enlarged UI scales interpolate the approved artwork; the native labels remain independently rasterized. This preserves the accepted faces without presenting this interim atlas as final portrait production.
