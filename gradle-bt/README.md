# Gradle Build Tool signature artwork

| File | What it is | PNG size |
|---|---|---|
| `gradle_bt_icon_primary.*` | The elephant alone | 605×445 |
| **`gradle_bt_lockup_panel.png`** | **Lockup on a white rounded panel — what the generator uses** | **676×203** |
| `gradle_bt_lockup_dark.*` | Lockup, dark wordmark, no panel | 640×167 |
| `gradle_bt_lockup_light.*` | Lockup, light wordmark, no panel | 640×167 |

## Why the lockup is panelled

The wordmark is near-black, so unlike the teal-only mark it cannot sit on both
grounds. **No email client inverts images**, so a PNG's polarity is fixed the
moment it is pasted — and the recipient's colour scheme is unknowable then.
Shipping a light-wordmark variant did not solve that, it only moved the failure
onto light-mode readers, who are still the majority.

So the signature lockup carries its own white ground: a rounded panel with the
corners left transparent. On a white background it is invisible and the logo
reads exactly as drawn; on a dark one it shows as a white card. One file,
correct either way. 676×203 around 640×167 of artwork, 18px padding, 14px radius.

The unpanelled `_dark` / `_light` pair is kept for other uses but is **not**
referenced by the generator. The mark is deliberately unpanelled — teal on
transparent already reads on both grounds.

**The PNGs are what the generator uses** — mail clients strip SVG, so a
signature cannot reference the vector. The SVGs are the source of truth for
producing any future size or variant.

## Provenance

| Here | From |
|---|---|
| `gradle_bt_icon_primary.svg` | `Gradle Build Tool Asset Pack/Icon Pack/SVG/Icon_Full_Colour.svg`, verbatim |
| `gradle_bt_lockup_dark.svg` | `by_develocity_mobile.svg`, verbatim |
| `gradle_bt_lockup_light.svg` | derived from it: the 24 ink fills (`black`, `#0A0C0D`) set to `#FFFFFF` |
| `gradle_bt_lockup_panel.png` | `gradle_bt_lockup_dark.png` composited onto the white rounded panel |

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

2. **Keep the unpanelled pair identical in size** if you use them together
   anywhere. The generator no longer swaps between them, so this no longer
   affects signatures, but a size mismatch would make the logo jump in anything
   that does.

When editing the light lockup's vector, leave the `fill="white"` alone — it is
a `<clipPath>` mask, not artwork.
