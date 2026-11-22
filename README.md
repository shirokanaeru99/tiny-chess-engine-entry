# tiny-chess-01 entry

A chess engine in 4,095 bytes of Python (main.py), built for the make.fun
"Build the strongest chess engine in 4 KB of Python" bounty.

main.py is an lzma-packed Python program: it unpacks and execs a negamax
engine with alpha-beta pruning, PVS, LMR, a transposition table,
quiescence search over captures and check evasions, MVV-LVA move
ordering, and piece-square-table evaluation on a 0x88 board. The search
is deterministic: a fixed budget of 45,000 nodes per move, no clock, no
randomness. It plays the gauntlet through the env at MAKEFUN_ENV_URL
(POST /game, POST /move) exactly as the starter does.

License: MIT (see LICENSE).
