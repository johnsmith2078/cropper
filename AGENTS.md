# Repository Guidelines

## Project Structure & Module Organization
- Single-page app: all HTML, CSS, and JavaScript live in `index.html`.
- UI shell, styles, and behavior are tightly coupled; keep new logic in the existing `<script>` block.
- The only runtime dependency is `JSZip` loaded from a CDN; all image processing runs fully in the browser.

## Build, Test, and Development Commands
- No build step is required. Open `index.html` directly in a browser.
- For local static hosting you may use any dev server, for example: `npx serve .` in the repo root.
- Always test changes in at least one Chromium-based browser (Chrome / Edge).

## Coding Style & Naming Conventions
- Use 2-space indentation for HTML, CSS, and JavaScript.
- Prefer plain ES6+ browser JavaScript (no frameworks, no bundlers).
- Use `camelCase` for variables and functions, `UPPER_SNAKE_CASE` for constants (e.g. `ROWS`, `COLS`).
- Keep DOM element variables descriptive (e.g. `fileInput`, `btnDownload`, `emojiCountEl`).
- Follow the existing comment style and keep comments brief and practical.

## Testing Guidelines
- There is no automated test suite; rely on manual testing.
- Verify that uploading a 4×6 emoji grid produces 24 centered tiles and a valid ZIP download.
- Test edge cases: transparent backgrounds, large images, nearly full-bleed content, and multiple files.
- Confirm that count labels and thumbnails update correctly when clearing and re-adding images.

## Commit & Pull Request Guidelines
- Follow the existing convention: short, single-line messages in Chinese that describe the change (e.g. “美化页面”, “裁剪后表情二次中心化”).
- Group related edits into a single commit; avoid mixing refactors and behavior changes without explanation.
- For pull requests, include: a concise description, before/after screenshots for UI changes, and manual test steps.
- Note any behavioral changes to cropping or centering so reviewers can focus validation on those flows.

## Agent-Specific Instructions
- Keep the project dependency-free except for `JSZip` via CDN.
- Do not introduce a build system or framework unless explicitly requested.
- Optimize for readability and offline use; the app should remain a single-file tool.
