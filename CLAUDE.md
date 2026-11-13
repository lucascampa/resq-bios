# CLAUDE.md

## How to communicate with me

- Take my words literally. Pay attention to every word I say.
- Don't infer broader context from what I say. If I say "maybe," it means maybe: discuss it, don't act on it.
- If something is ambiguous, ask. Don't guess.
- Do what I ask, nothing more. If I say you don't have to do anything, don't.

## For the AI assistant building this page

- [README.md](README.md) is the spec. Build what's there.
- Keep it static: plain HTML and CSS, no framework, no build step, no backend. JavaScript is limited to the small inline script for the copy-email button.
- Never write bio details that the person hasn't given you.
- Where a field says `[TODO]`, leave a visible placeholder in the page. Don't fill it in.
- New bios arrive as a document split into keywords, short and expanded (see `lucas bio.md`). Use the wording as written.

## Publishing

- Live at https://lucascampa.github.io/resq-bios/, served by GitHub Pages from `main`, folder root. Repo: `lucascampa/resq-bios` (public).
- To update: edit, commit and push to `main`. Don't rename the repo or change the branch, because the URL is meant to go in a QR code.
- Always ask before pushing, every time, without exception. A push publishes to the live site.
- The repo holds the site files (`index.html`, `styles.css`, the images the page uses), plus `README.md`, `CLAUDE.md` and `.gitignore`. `lucas bio.md` and `images/bg*.png` stay local and are listed in `.gitignore`. Don't commit them.
- End commit messages with: `Co-Authored-By: Claude Sonnet 5.5 <noreply@anthropic.com>`
