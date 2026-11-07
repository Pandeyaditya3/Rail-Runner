# Rail Runner

A fast, one-file endless runner. You sprint down three forest railway tracks, dodge trains and obstacles, and collect coins. Everything is drawn in code on an HTML canvas, so there are no images or build steps.

## Play

Open `rail-runner.html` in any modern browser. It works offline. The only online asset is the Rubik font from Google Fonts, and the game falls back to a system font without it.

## Controls

| Action | Touch | Keyboard |
|---|---|---|
| Change lane | Swipe left or right | Left / Right arrows, or A / D |
| Jump | Swipe up | Up arrow, W, or Space |
| Roll | Swipe down | Down arrow or S |
| Pause / resume | Tap anywhere | P or Esc |
| Start / play again | Tap | Space or Enter |

The game also pauses automatically when you switch apps or tabs.

## Obstacles

- **Trains** fill a lane. Switch lanes to avoid them, because you cannot jump over them.
- **Orange hazard barriers** are low. Jump over them.
- **Red-and-white gantries** are overhead. Roll underneath.
- **Coins** appear on the ground and in the air. Jump to catch the high ones.

The game speeds up the longer you survive, from a start speed of 14 up to a cap of 36.

## Scoring

Score is distance travelled. Your best score is saved in the browser (`localStorage`, key `rr_best`), so it stays between sessions on the same device.

## Features

- Forest scene with a sunrise sky, mist, distant hills and trees beside the track
- Shaded trains with headlights and windows, hazard barriers, flashing signal gantries and spinning coins
- Animated runner that leans into lane changes and tucks into a roll
- Particle effects for dust, coin sparkles and crashes, plus screen shake
- Synthesized sound effects (no audio files)
- Safe-area aware layout for phones and tablets with notches
- Tap-to-pause with a pause button and overlay

## Performance

The canvas resolution is capped at 1.5x the screen size so tablets and high-density phones stay smooth. The screen-edge shading is drawn once and reused each frame.

## Customizing

All the code is in one `<script>` block. Useful places to tweak:

| What | Where |
|---|---|
| Start speed, top speed, acceleration | `reset()` and `update()` (`speed=14`, `Math.min(36, ...)`) |
| Obstacle mix and spacing | `spawnRow()` |
| Gravity and jump height | `update()` (`p.vy-=34*dt`) and `jump()` (`p.vy=11`) |
| Swipe sensitivity and tap size | `pointerup` handler (25 px threshold) |
| Colors and scenery | `drawSky()`, `drawTrack()` |
| Runner look | `drawPlayer()` |
| Sound effects | `snd()` calls |

## Files

- `rail-runner.html`: the whole game (HTML, CSS and JavaScript)
- `README.md`: this file


you can play from here:
https://pandeyaditya3.github.io/Rail-Runner/
