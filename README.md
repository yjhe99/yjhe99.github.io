# Personal website — how to edit & publish

Your whole site is **one file: `index.html`**. No build tools, no frameworks.
Open it in any text editor and everything you'd want to change is at the very top.

## How to change the content

1. Open `index.html`.
2. Find the block near the top marked **`✏️ EDIT YOUR CONTENT HERE`** (it's the `const SITE = { ... }` part).
3. Change the text between the quotes. Save. Refresh the page in your browser to see it.

That block is the only part you normally touch — everything below it is styling and code that makes the page draw itself.

### Common edits

- **Add a photo:** put a file named `profile.jpg` in this folder (square photos look best). Until you do, your initials show instead.
- **Fill in your links:** in `links:`, paste your real Google Scholar / LinkedIn / GitHub URLs between the quotes. Leave any as `""` to hide that button.
- **Add a publication:** copy one `{ ... }` line inside `publications: [ ... ]`, paste it, and edit. Keep the comma between entries.
- **Bold your name:** wrap it in double stars, e.g. `**He, Y.**` — it shows bold in the author list.
- **Add a link to a paper or patent:** paste the URL into that entry's `link: "..."` field. The title becomes clickable (and the figure links too). Leave `""` for no link.
- **Show your contribution on a paper:** fill a publication's `role:` field (e.g. `"NGS data analysis & MD simulation"`). It shows as a small "My contribution — …" tag under that entry, which makes the list read as *your computational role on these teams* rather than just the paper topics. Leave `""` to show no tag. Some are pre-filled from your CV — verify them and fill the blanks accurately.
- **Add a figure to a publication:** put the image in the `figures` folder and set that publication's `figure:` field to its filename, e.g. `figure: "figures/pub1.png"`. The **whole image is always shown** — nothing is cropped, portrait or landscape. Leave `""` for no figure. A missing/typo'd file simply shows no figure (no broken image).
- **Make figures bigger/smaller:** in the `<style>` block find `.pub-fig { flex: 0 0 220px; ... }` and change `220px`.
- **Add a link anywhere in text** (e.g. About): write `[the visible words](https://the-url.com)`. That's how "Prof. Tim Yeh" is linked.
- **Hide a whole section:** set its list to empty — e.g. `presentations: []`. The section and its menu link disappear automatically.
- **Edit the "Life" page:** it's the `life:` block. `intro` is the opening line, `paragraphs` is a list (one string = one paragraph), and `photos` is an optional list of image files (e.g. `"figures/life1.jpg"`) shown in a grid. To remove the Life page and its menu link entirely, set `life: null,`.
- **Change the accent color:** near the top of the `<style>` block, edit `--accent: #7a4b2b;` to any hex color. (There's also a dark-mode color right below it.)

### About the sections
- **Selected Publications & Patents** and **Teaching & Mentoring** are each one section that draws from two lists (`publications` + `patents`, and `teaching` + `mentoring`). Edit each list on its own; they're joined automatically under one heading.
- **Mentoring format:** each mentee is `{ name, major, time, role }` and shows as *Name — major ’YY · time · role*. Leave `role: ""` blank until they land somewhere; blank parts are skipped.
- **Research interests** are the bullet list in About — edit the `interests:` list.
- **Your photo** is auto-compressed for the web. If you replace `profile.jpg`, keep it small (a few hundred KB); a full-resolution photo will make the page slow. Your original is saved as `profile_original.jpg`.

## How to publish on GitHub Pages

1. Put `index.html`, `cv.pdf`, and (optionally) `profile.jpg` in your repository.
2. On GitHub: **Settings → Pages → Build and deployment → Source: “Deploy from a branch”**, pick `main` and `/ (root)`, then Save.
3. Wait ~1 minute. Your site is live at the URL GitHub shows on that Pages screen.

If your repo is named exactly `yourusername.github.io`, the site is served at
`https://yourusername.github.io/`. Otherwise it's `https://yourusername.github.io/repo-name/`.

### Publish updates later
Every time you edit and push `index.html` to the repo, the live site updates in about a minute.
