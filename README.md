# chess-88-final

Single-file 0x88 chess engine, packed to fit the make.fun entry budget.

- `main.py` — entry point, ~3.9 KB, payload is base85 + LZMA (`format=2`), expanded at import
- Search: PVS / alpha-beta with fixed 200,000 nodes per move, deterministic move choice
- Protocol: `agent-fun/bars-replay/v1`, newline-delimited JSON on stdin/stdout
  - `hello` → `{"ready":true}`
  - batch `{"seq":1,"game":1,"fen":"...","legal_moves":[...],"status":"your_move"}` → `{"seq":1,"move":"e2e4"}`
- No third-party dependencies, Python 3 stdlib only
- License: MIT (see LICENSE)
