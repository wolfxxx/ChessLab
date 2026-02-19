# Chess Lab

A single-file browser chess app (`index.html`) with a playable board, visual themes, custom piece sets, animation, move history navigation, opening book support, and an in-browser chess engine.

## Highlights

- Single-file app: no build step required
- Play vs bot (default) or human
- Multiple board themes and piece styles
- External piece pack support (folder path or ZIP import)
- Smooth move animation for both human and bot
- Full legal move support:
  - Castling
  - En passant
  - Promotion (with underpromotion picker)
- Timeline navigation (`Back` / `Forward`) with animation
- Opening recognition and book continuations display
- Hint button for best-move suggestion
- Post-move quality feedback (`Best / Inaccuracy / Mistake / Blunder`)
- FEN load/copy support

## Quick Start

1. Clone/download this repo.
2. Open `index.html` in your browser.
3. Start playing.

No install, server, or dependencies required.

## Controls

- `New Game`: reset to standard start position
- `Undo`: undo last move
- `Flip Board`: flip orientation
- `Hint`: show best move for current position
- `Back` / `Forward`: inspect game history with animation
- `Load FEN` / `Copy FEN`: import/export current position

## Opponent & Strength

- `Opponent`
  - `Random Bot (Black)` (default)
  - `Human`
- `Bot Strength`
  - Easy (Depth 2)
  - Medium (Depth 3)
  - Hard (Depth 4)
  - Expert (Depth 5)

Engine uses minimax + alpha-beta pruning with additional search/eval improvements.

## Piece Styles & External Packs

Built-in styles include multiple glyph/SVG quality sets and horse-themed knight variants.

### Import ZIP pack

1. Click `Import ZIP` (or drop ZIP into drop zone).
2. The app extracts piece files locally in-browser.
3. Switch `Piece Style` to `External Pack`.

### Folder-based external pack

- Set `Pack Path` (example: `piece-packs/cburnett`)
- Choose `Pack Format` (`svg`, `png`, etc.)
- Choose `Naming` mode (`Auto Detect`, `wK`, `wk`, `color_name`)

## Move Quality Feedback

After a human move, the app analyzes the played move against the engine best move and reports:

- `Best`
- `Inaccuracy`
- `Mistake`
- `Blunder`

Opening-book moves are labeled `Book move` instead of being penalized.

## Opening Book

- Opening names shown in status/book area when recognized
- Includes practical coverage for common openings and early branches
- Tooltip includes possible continuations from current book context

## Technical Notes

- Core implementation is in `index.html`
- State is represented as chess position + move history + timeline snapshots
- Engine includes:
  - Iterative deepening
  - Alpha-beta pruning
  - Quiescence search
  - Move ordering (history/killers)
  - Transposition table (Zobrist hashing)
  - Basic opening book integration

## Known Limits

- Not yet a full PGN workflow (import/export)
- No clock/time-control system yet
- No tablebase probing yet
- Engine strength is improved but still far below top engines

## Suggested Next Steps

- PGN import/export and game analysis report
- Time controls and clock UI
- Blunder-check / best-line preview mode
- Stronger evaluation terms and pruning improvements
- Optional local opening database and endgame tablebase integration

## License

No license file is included yet. Add one if you want reuse terms to be explicit.
