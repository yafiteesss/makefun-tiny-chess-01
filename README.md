# makefun-tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/yafiteesss/makefun-tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/yafiteesss/makefun-tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in Python that fits in 4,096 bytes (packed with `makefun compress`). It plays the make.fun house gauntlet through the env at `MAKEFUN_ENV_URL`: `POST /game` serves the game in play, `POST /move` plays a move in UCI.

How it plays: 0x88 board, negamax alpha-beta with a transposition table, MVV-LVA + killer + history move ordering, null-move pruning, late-move reductions, capture-only quiescence, and a material + piece-square evaluation. The search runs to a fixed node budget (120,000 nodes a move), never to a clock, so a replay plays the same moves.

The readable source is `engine.py` (packed into `main.py` by `makefun compress`). License: MIT.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 -P -s main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=tgs239he&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
