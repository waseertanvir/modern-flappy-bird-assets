# Modern Flappy Bird Assets

A modern, smooth 3D-cartoon style asset set for a Flappy Bird-inspired game. Every sprite is a PNG cut directly from the original sprite sheet, so it matches the design exactly.

![Modern Flappy Bird sprite sheet](assets/modern-flappy-bird-sprite-sheet.png)

## What is in here

| Folder | Contents |
| --- | --- |
| `assets/birds/` | The bird in three wing poses (`bird_flap_0` wings up, `bird_flap_1` mid, `bird_flap_2` down). All on the same 255 x 245 canvas and aligned on the beak, so they can be swapped frame by frame without jitter. |
| `assets/png/` | Pipes, coin, replay button, score badge, ground and sky. |
| `assets/modern-flappy-bird-sprite-sheet.png` | The original concept sheet everything was cut from. |

## Sprites

| File | Size | Notes |
| --- | --- | --- |
| `pipe_cap_top.png` | 197 x 86 | Pipe end with the opening facing up (a pipe rising from the ground). |
| `pipe_cap_bottom.png` | 199 x 93 | Pipe end with the opening facing down (a pipe hanging from the ceiling). |
| `pipe_body.png` | 165 x 420 | Pipe shaft. Repeat it vertically to reach any height. |
| `pipe_long.png`, `pipe_short.png` | 199 x 615, 181 x 397 | Complete pipes with a cap on both ends, for decoration. |
| `coin.png` | 140 x 147 | Collectible coin. |
| `button_replay.png` | 216 x 209 | Replay button. |
| `score_badge.png` | 377 x 165 | Empty score frame. Draw the score text on top with your own font. |
| `ground_tile.png` | 1033 x 156 | Grass and soil strip. Repeat it horizontally for a scrolling floor. |
| `background_sky.png` | 754 x 346 | Sky, clouds and hills. The only sprite without transparency. |

## Using the assets

- **Building a pipe:** place `pipe_cap_top` at the gap edge, then stack `pipe_body` below it, centred under the cap. Do the same with `pipe_cap_bottom` for the upper pipe.
- **Scrolling:** move `ground_tile` and `background_sky` left and wrap around. Move the sky slower than the ground for a parallax effect. If the sky shows a seam when it wraps, alternate it with a horizontally mirrored copy.
- **Animating the bird:** cycle `bird_flap_0`, `bird_flap_1`, `bird_flap_2`, `bird_flap_1`.

## Source inspiration

The visual direction was inspired by [samuelcust/flappy-bird-assets](https://github.com/samuelcust/flappy-bird-assets). This is a modern reinterpretation and is not the original pixel-art asset pack.

## License

Released under the [MIT License](LICENSE).
