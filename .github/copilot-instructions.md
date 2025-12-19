<!-- GitHub Copilot / AI agent guidance for the WebDevIt project -->
# Copilot instructions — WebDevIt

Summary
- This repository is a collection of static HTML demos and small pages organized by folders (e.g. `chapter1/`, `chapter3real/`, `chapter5/`). There is no build system, package manager, or automated tests.

Big picture
- Static artifacts: HTML files are the primary source. CSS lives under folders like `chapter3real/css/style.css`; media assets are in `media/` or `Media/` subfolders.
- Project intent: learning/examples—not a packaged web app. Changes should preserve relative paths and file names because pages link to assets by relative paths.

Where to look (examples)
- Layout/CSS examples: `chapter3real/css/style.css`
- Flexbox demo: `chapter5/FlexBlock/Flexbox.html`
- Profile card examples: `PF/Profile Card.html` and `ass2-2-2/Profile Card.html`
- Contact form demo: `Contact Form/Contact Form.html`

Conventions & important patterns
- Many filenames and folders contain spaces and inconsistent casing (e.g., `Media/` vs `media/`, `Assitement/` vs `Assitement`). On Windows this hides problems; avoid renaming or re-casing files without explicit user approval.
- Pages use relative links to local assets. Always maintain relative link correctness when moving or refactoring files.
- There are duplicate or similarly named folders (e.g., multiple `Assitement` variants). Confirm intent before consolidating.

Developer workflows (how to preview/test changes)
- Quick preview (recommended): install VS Code Live Server extension and open any HTML file with Live Server.
- Minimal static server (cross-platform): from the repository root run:
```
python -m http.server 8000
```
then open `http://localhost:8000/chapter5/FlexBlock/Flexbox.html` in a browser.
- No `npm`, `make`, or CI found. Do not add tooling without asking the repo owner.

What AI agents should do first
- Inspect a target page (example: `chapter5/FlexBlock/Flexbox.html`) to understand the relative asset layout before editing.
- If modifying markup or assets, run a local preview (Live Server or `http.server`) to validate visual changes.
- When proposing structural renames (paths, folder names, case normalization), create a migration plan and list all affected files before applying.

Integration points & external deps
- No external services, build tools, or package manifests detected. Images and CSS are local files. External CDN links may exist inside some HTML files — only update them if necessary and document the change.

Restrictions and safety
- Do not perform bulk renames or automated casing fixes. Ask the user first — the repo contains many similarly named folders and files.
- Preserve original file encodings and line endings (Windows environment). Keep changes minimal and scoped.

If you update this guidance
- If you find an existing `.github/copilot-instructions.md` or other agent docs, merge and preserve any usage examples. This file was created to provide an up-to-date baseline.

Questions for the user
- Do you want me to normalize filenames/cases across the repo, or keep the current layout as-is?
- Should I add a simple `README.md` at the repository root explaining preview steps for contributors?

— end of guidance —
