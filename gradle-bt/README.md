# Gradle Build Tool signature artwork

| File | What it is | PNG size |
|---|---|---|
| `gradle_bt_icon_primary.*` | The elephant alone | 605×445 |
| `gradle_bt_lockup_dark.*` | Full lockup, **dark** wordmark — for light mail | 640×167 |
| `gradle_bt_lockup_light.*` | Full lockup, **light** wordmark — for dark mail | 640×167 |

**The PNGs are what the generator uses** — mail clients strip SVG, so a
signature cannot reference the vector. The SVGs are the source of truth for
producing any future size or variant.

## Provenance

| Here | From |
|---|---|
| `gradle_bt_icon_primary.svg` | `Gradle Build Tool Asset Pack/Icon Pack/SVG/Icon_Full_Colour.svg`, verbatim |
| `gradle_bt_lockup_dark.svg` | `by_develocity_mobile.svg`, verbatim |
| `gradle_bt_lockup_light.svg` | derived from it: the 24 ink fills (`black`, `#0A0C0D`) set to `#FFFFFF` |

The PNGs were rasterised from a 1884×491 export of the same lockup, not from
these vectors — no SVG rasteriser was available that didn't need native cairo.
They match the vectors, but if you ever regenerate them, do it from the SVG.

## Colours

The elephant is a gradient, **`#209BC4` → `#4DC9C0`** (midpoint `#36B2C2`).
The swoosh in "develocity" is `#2CA7BE`, Develocity's own teal — correct in a
co-brand lockup.

The generator does **not** use any of these directly: its accent is `#29828C`,
that hue darkened to clear WCAG AA as body text on a white mail background.

## Two rules

1. **Paths are permanent.** Once a signature is pasted into someone's mail
   client its image URL is baked in and can never be corrected. Never rename,
   move or delete a file here once its generator has gone out — add instead.

2. **The lockup pair must stay identical in size.** The dark-preview toggle
   swaps `_dark` for `_light`, so any mismatch makes the logo jump.

When editing the light lockup's vector, leave the `fill="white"` alone — it is
a `<clipPath>` mask, not artwork.
