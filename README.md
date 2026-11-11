# FaceRefine Plus Tests

Measured, side-by-side tests of [ComfyUI-H3-FaceRefine-Plus](https://github.com/AnniCodex/ComfyUI-H3-FaceRefine-Plus)
and of method B against the official [ComfyUI-H3-FaceRefine](https://github.com/Carasibana/ComfyUI-H3-FaceRefine),
on small and medium faces in MiniMax H3 video shots.

**Open the test page:** https://annicodex.github.io/FaceRefine-Plus-Tests/ (the videos play inline there).

This repository holds no code: only the test videos (`videos/`), their poster frames (`posters/`) and the page
(`index.html`).

## What is tested

| Test | Face | Compared |
|---|---|---|
| mara (example assets of the FaceRefine Plus repo) | 41-62 px | H3 original, official FaceRefine, FaceRefine Plus 0.15 and 0.30, method B + Plus |
| Vespa shot (clip C05 of a music video) | 92-110 px | H3 original, official FaceRefine, FaceRefine Plus 0.15 and 0.30, method B + Plus |

Every refine of a shot uses the same shot, prompt, reference pictures and seed. Measured: wobble, face sharpness,
colour shift vs the original, ArcFace identity vs the character's close-ups, real render time on one RTX 5090.

## Results in short

| | mara: official | mara: Plus 0.15 | mara: Plus 0.30 | Vespa: official | Vespa: Plus 0.15 |
|---|---|---|---|---|---|
| Wobble | 0.70 % | **0.42 %** | 0.45 % | 0.20 % | **0.12 %** |
| Face sharpness | 1613 | **2979** | 2948 | 481 | **1094** |
| Colour (dL / db) | -0.9 / -2.2 | **-0.2 / -0.5** | **-0.2 / -0.5** | -1.1 / -1.8 | **-0.3 / -0.2** |
| Identity vs close-ups | 0.60 | 0.41 | **0.68** | **0.44** | 0.43 |
| RTX 5090 | 87 s | 256 s | 239 s | 92 s | 210 s |

Method B on the four example characters: mean identity of the refined wide shot vs the close-ups 0.55 → **0.65**.
The page has every video, the settings used and the full tables.

## Videos

| File | Shows |
|---|---|
| `comparison_mara_official_zoom.mp4` | face zooms: original, official, Plus 0.15, Plus 0.30 |
| `comparison_mara_official_fullframe.mp4` | whole frame + zooms: original, official, Plus |
| `comparison_mara_full_official.mp4` | whole frame: original, official |
| `comparison_mara_full_official_vs_plus.mp4` | whole frame: official, Plus 0.15 |
| `comparison_mara_full_official_vs_plus030.mp4` | whole frame: official, Plus 0.30 |
| `comparison_mara_strength.mp4` | whole frame + zooms: original, official, Plus 0.15, Plus 0.30 |
| `comparison_mara.mp4` | zooms: original, Plus, method B original, method B + Plus |
| `comparison_mara_fullframe.mp4` | whole frame + zooms: original, Plus, method B + Plus |
| `comparison_mara_full_plus.mp4` | whole frame: original, Plus |
| `comparison_mara_full_method_b.mp4` | whole frame: original, method B + Plus |
| `comparison_vespa_fullframe.mp4` | whole frame + zooms: original, official, Plus, method B + Plus |
| `comparison_vespa_zoom.mp4` | zooms: original, official, Plus, method B + Plus |
| `comparison_vespa_strength.mp4` | whole frame + zooms: original, official, Plus 0.15, Plus 0.30 |
| `comparison_vespa_full_official.mp4` | whole frame: original, official |
| `comparison_vespa_full_plus.mp4` | whole frame: original, Plus |
| `comparison_vespa_full_official_vs_plus.mp4` | whole frame: official, Plus |
| `comparison_vespa_full_method_b.mp4` | whole frame: original, method B + Plus |
| `comparison.mp4` | the first comparison, earlier settings: original, official, Plus 0.30 + Flow Lock + Tone Match, latent hires |

## Credits and copyright

- [ComfyUI-H3-FaceRefine](https://github.com/Carasibana/ComfyUI-H3-FaceRefine) by Carasibana.
- FaceRefine Plus and method B: [ComfyUI-H3-FaceRefine-Plus](https://github.com/AnniCodex/ComfyUI-H3-FaceRefine-Plus).
- The mara, teo, ines and bruno characters are invented and were made from scratch for the FaceRefine Plus repo
  (Krea 2, Qwen Image 2.1 Edit, MiniMax H3). They do not show real people.
- **The Vespa clips** (`comparison_vespa_*.mp4` and `comparison.mp4`) are taken from a music video by Annistupendi
  Music and are **© Annistupendi Music, all rights reserved**. They are shown here only to document these tests.
  Full video on YouTube: https://www.youtube.com/watch?v=8_gSLNxd2EE
