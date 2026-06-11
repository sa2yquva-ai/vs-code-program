# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A browser-based game project. Currently contains a 2-player Tic Tac Toe game (`tictactoe.html`). All code lives in self-contained HTML files — no build tools, no package manager, no server required. Open any `.html` file directly in a browser to run it.

## Architecture

Each game is a **single HTML file** with inline CSS and vanilla JavaScript — no external dependencies, no frameworks. The pattern is:

- **CSS** in `<style>` — dark theme using CSS variables-style color constants (`#1a1a2e`, `#e94560`, `#a8dadc`)
- **HTML** — static structure only; all dynamic content driven by JS
- **JavaScript** in `<script>` — plain JS, no modules, state held in top-level `let` variables

### Tic Tac Toe (`tictactoe.html`)
- `board`: flat 9-element array representing the grid (index 0–8)
- `wins`: hardcoded array of all 8 winning index triplets
- `init()`: resets board and DOM; preserves `scores` object across rounds
- `checkWinner()`: iterates `wins` array; returns winner + winning line, or `'tie'`, or `null`
- Cell clicks guarded by `gameOver` flag and `board[i]` occupancy check

## Git Workflow

**After every piece of work — no exceptions — commit and push immediately.** Never leave completed work uncommitted. This ensures we always have a saved version on GitHub and can revert to any previous state if something breaks.

Steps after each change:
```
git add <files>
git commit -m "<type>: <short description>"
git push
```

Commit message types: `feat` (new feature), `fix` (bug fix), `style` (visual/CSS only), `refactor` (restructure without behavior change).

Commit granularity: one logical change per commit. If adding a feature and fixing a bug in the same session, make two separate commits — not one combined commit.

Remote: `https://github.com/sa2yquva-ai/vs-code-program`
