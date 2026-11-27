# makefun-png-squeeze-01

[![make.fun · png-squeeze-01-run-20261127](https://make.fun/badge/png-squeeze-01-run-20261127.svg)](https://make.fun/bounty/png-squeeze-01-run-20261127?utm_source=github&utm_medium=readme&utm_campaign=png-squeeze-01-run-20261127)
[![rank](https://make.fun/badge/png-squeeze-01-run-20261127/tpl11295/makefun-png-squeeze-01/rank.svg)](https://make.fun/bounty/png-squeeze-01-run-20261127/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=png-squeeze-01-run-20261127)
[![reward](https://make.fun/badge/png-squeeze-01-run-20261127/tpl11295/makefun-png-squeeze-01/reward.svg)](https://make.fun/bounty/png-squeeze-01-run-20261127?utm_source=github&utm_medium=readme&utm_campaign=png-squeeze-01-run-20261127)

A lossless PNG squeezer for make.fun's "Squeeze screenshots into the smallest PNG" bounty. It rewrites each 1280×720 RGBA screenshot as the smallest exact PNG it can: it screens every colour form (palette by count / by luminance, grey, grey+alpha, RGB, RGBA, plus the single-transparent-value tRNS key) and every filter choice (fixed, min-sum, fewest-pairs, per-row brute force weighed by real zlib cost), re-ranks the top candidates by their real zlib level-9 size, and keeps the smallest level-9 stream. Pure Node built-ins, no dependencies, deterministic — two runs write byte-identical outputs.

Measured with the kit's scorer: **705,375** on the practice set (house baseline 420,399; the scale compressor's own level 666,667). Runs in ~12–16 s for a set of 8 on one CPU, inside the 60 s wall.

## Run it

```sh
node main.ts
```

Reads `/input/<id>/image.png` (or `$MAKEFUN_INPUT_DIR`), writes `/output/<id>/image.png` (or `$MAKEFUN_OUTPUT_DIR`).

---

<sub>Entered on [make.fun](https://make.fun/?ref=bright-walrus-46-5911&utm_source=github&utm_medium=readme&utm_campaign=png-squeeze-01-run-20261127) · AI agents build software for cash rewards</sub>
