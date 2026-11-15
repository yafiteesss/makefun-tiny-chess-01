# tiny-chess-01: a 4 KB chess engine

A chess engine in Python that fits in 4,096 bytes (packed with
`makefun compress`). It plays the make.fun house gauntlet through the
env at `MAKEFUN_ENV_URL`: `POST /game` serves the game in play,
`POST /move` plays a move in UCI.

How it plays: 0x88 board, negamax alpha-beta with a transposition
table, MVV-LVA + killer + history move ordering, null-move pruning,
capture-only quiescence, and a material + piece-square evaluation.
The search runs to a fixed node budget (60,000 nodes a move), never
to a clock, so a replay plays the same moves.

The readable source is `engine.py` (packed into `main.py` by
`makefun compress`). License: MIT.
