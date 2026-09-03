# Brand assets

Public artwork for the email signature generators. **This repo is public on
purpose and holds nothing else.**

Mail clients fetch signature images with no session of their own — Gmail proxies
them — so signature artwork has to sit somewhere a stranger can reach. The
design work itself lives in a private repo; only these files are public.

| Folder | Used by |
|---|---|
| `develocity/` | Develocity email signature generator |
| `gradle-bt/` | Gradle Build Tool email signature generator |

Served at:

```
https://hclayton-brand.github.io/brand-assets/<folder>/<file>
```

## Two rules

1. **Paths are permanent.** Once a signature is pasted into someone's mail
   client, its image URL is baked in and can never be corrected — mail already
   sitting in inboxes can't be reached. Never rename, move or delete a file
   here once its generator has gone out. Add new files instead.

2. **Each lockup pair must be identical artwork at identical pixel size.** The
   generators' dark-preview toggle swaps `_dark` for `_light`, so any size
   difference makes the logo jump when a reader switches theme.

`_dark` = dark wordmark, for light backgrounds. `_light` = light wordmark, for
dark backgrounds.
