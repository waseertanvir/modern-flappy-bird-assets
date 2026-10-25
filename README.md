# Modern Flappy Bird Assets

A modern, smooth 3D-cartoon style asset set for a Flappy Bird-inspired game. Every sprite is a PNG cut from the original sprite sheet. Most are upscaled 4x with the [Real-ESRGAN](https://github.com/xinntao/Real-ESRGAN) AI upscaler, so they keep the exact design but stay sharp on high-resolution screens. The ground and sky tiles are kept near the sheet's resolution and edited to scroll seamlessly.

![Modern Flappy Bird sprite sheet](assets/modern-flappy-bird-sprite-sheet.png)

## What is in here

| Folder | Contents |
| --- | --- |
| `assets/birds/` | The bird in three wing poses (`bird_flap_0` wings up, `bird_flap_1` mid, `bird_flap_2` down). All on the same 1020 x 980 canvas and aligned on the beak, so they can be swapped frame by frame without jitter. |
| `assets/png/` | Pipes, coin, replay button, score badge, ground and sky. |
| `assets/modern-flappy-bird-sprite-sheet.png` | The concept sheet everything was cut from, upscaled 4x to 6144 x 4096. |

## Sprites

| File | Size | Notes |
| --- | --- | --- |
| `pipe_cap_top.png` | 788 x 344 | Pipe end with the opening facing up (a pipe rising from the ground). |
| `pipe_cap_bottom.png` | 796 x 372 | Pipe end with the opening facing down (a pipe hanging from the ceiling). |
| `pipe_body.png` | 660 x 1680 | Pipe shaft. Repeat it vertically to reach any height. |
| `pipe_long.png`, `pipe_short.png` | 796 x 2460, 724 x 1588 | Complete pipes with a cap on both ends, for decoration. |
| `coin.png` | 560 x 588 | Collectible coin. |
| `button_replay.png` | 864 x 836 | Replay button. |
| `score_badge.png` | 1508 x 660 | Score frame with placeholder `0000` digits, as on the sheet. |
| `ground_tile.png` | 779 x 152 | Grass and soil strip. Tiles seamlessly, so repeat it horizontally for a scrolling floor. |
| `background_sky.png` | 539 x 346 | Sky, clouds and hills. Fully opaque, and tiles seamlessly horizontally. |

## Using the assets

- **Building a pipe:** place `pipe_cap_top` at the gap edge, then stack `pipe_body` below it, centred under the cap. Do the same with `pipe_cap_bottom` for the upper pipe.
- **Scrolling:** move `ground_tile` and `background_sky` left and wrap around. Move the sky slower than the ground for a parallax effect. Both tiles wrap with no seam.
- **Animating the bird:** cycle `bird_flap_0`, `bird_flap_1`, `bird_flap_2`, `bird_flap_1`.
- **Smaller sizes:** the upscaled sprites are large so they hold up on any screen. Scale them down in your engine, or resize them once with a high-quality filter if you need smaller files.

## How the sprites were made

Each sprite except the ground and sky tiles was cut from the original 1536 x 1024 sprite sheet, then upscaled 4x with [Real-ESRGAN](https://github.com/xinntao/Real-ESRGAN), using the [realesrgan-ncnn-vulkan](https://github.com/xinntao/Real-ESRGAN-ncnn-vulkan) build and the general-purpose `realesrgan-x4plus` model. That model was chosen over the anime model because it keeps the soft 3D shading instead of adding dark outlines. The sprite sheet itself was upscaled the same way. The ground and sky tiles were instead cut from the sheet and edited so their left and right edges match, which lets them repeat without a visible join.

For the transparent sprites, color and transparency were upscaled separately. Before upscaling, the edge pixels left over from the sheet's white background were repainted with the sprite's own colors, so there is no white outline on dark backgrounds.

## Source inspiration

The visual direction was inspired by [samuelcust/flappy-bird-assets](https://github.com/samuelcust/flappy-bird-assets). This is a modern reinterpretation and is not the original pixel-art asset pack.

## License

Released under the [MIT License](LICENSE).
