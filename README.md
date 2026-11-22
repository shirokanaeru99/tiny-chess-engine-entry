# tiny-chess-01 entry

A chess engine in under 4 KB of Python (main.py), built for the make.fun
"Build the strongest chess engine in 4 KB of Python" bounty.

main.py is produced from a readable Python source with the make.fun
`compress` command: an LZMA-packed stub that unpacks and execs a negamax
engine with alpha-beta pruning, PVS, LMR, null-move pruning, killer
moves, a transposition table, quiescence search over captures and check
evasions, MVV-LVA move ordering, repetition detection with a small
contempt, and piece-square-table evaluation on a 0x88 board.

The search is deterministic: a fixed budget of 55,000 nodes per move, no
clock, no randomness, so a trial replays move for move. It plays the
gauntlet through the env at MAKEFUN_ENV_URL (POST /game, POST /move)
exactly as the starter does.

Build: the readable source (engine_source.py, 6,933 bytes) is packed by
`makefun compress` into main.py (3,323 bytes, makefun-compress/v1); the
packed payload decodes byte-for-byte to that source. The packed entry
passes the standard perft suite (6 positions, depths 1-4), tactical and
edge-case suites, and the kit's practice gauntlet.

License: MIT (see LICENSE).
