# Quaternius Ultimate Stylized Nature Pack

Source: https://quaternius.com/packs/ultimatestylizednature.html

Creator: Quaternius (laulhet@gmail.com)

Original release: May 2022

License: Creative Commons Zero v1.0 Universal (CC0-1.0)
https://creativecommons.org/publicdomain/zero/1.0/

The source page identifies the pack as 60+ textured nature assets with seamless textures and
normal maps, available in glTF and free for personal and commercial use. This directory keeps a
small, deliberately selected runtime subset under its original filenames. No endorsement by the
creator is implied.

## The subset kept here

Retrieved from the pack's glTF folder on 2026-08-12. Files are otherwise under their original
names, and the rest of the 60+ asset pack is deliberately not vendored.

| Kept | Why |
|---|---|
| `BirchTree_1`–`BirchTree_5` | Five silhouettes off one shared set of textures, so variety costs mesh data only. |
| `DeadTree_1`, `DeadTree_2` | Bare trunks for the outer rings, where the Reach is meant to read as wilder. |
| `Bush`, `Bush_Large`, `Bush_Small` | Three shrub sizes, all sharing `Bush_Leaves.png`. |
| `BirchTree_Bark*`, `BirchTree_Leaves`, `Bush_Leaves` | The textures the birches and bushes reference. |
| `NormalTree_Bark`, `NormalTree_Bark_Normal` | The only textures the dead trees reference. |

## Local modifications

CC0 permits modification, but this file would otherwise claim the assets are as shipped, so the
changes are recorded here.

Both bark normal maps arrived as 16-bit RGBA PNGs and were re-encoded to 8-bit RGB on 2026-08-12.
Nothing was resampled and the dimensions are unchanged at 2048x2048: the alpha channel was a
constant 255 and carried no information, and the extra eight bits per channel cannot survive
import, which compresses these maps to BC5 at eight bits per channel regardless.

| File | Before | After |
|---|---|---|
| `BirchTree_Bark_Normal.png` | 21.7 MB | 5.3 MB |
| `NormalTree_Bark_Normal.png` | 18.2 MB | 3.6 MB |

The two new textures are imported with mipmaps generated and, for the normal map, VRAM
compression and the normal-map path — matching the birch pair rather than the flat defaults a
headless import pass produces before anything has rendered them in 3D.
