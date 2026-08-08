# Academic job-market website

This is a one-page static website built with plain HTML and CSS. It has no build step or third-party code and can be published on GitHub Pages or Cloudflare Pages.

## The two files you will edit most often

- `index.html` contains the actual words, links, sections, and file references shown on the webpage.
- `styles.css` controls appearance: widths, spacing, colors, type sizes, borders, and mobile layout.

The `assets` folder stores files such as the photo, CV, paper, and figures. Putting a file in `assets` does **not** automatically add it to the webpage; `index.html` still needs a link or image element that points to that file.

You can edit both files with any plain-text editor, including Notepad, Visual Studio Code, or the GitHub web editor. Save the file and refresh your browser to see the change.

## Edit text and contact information

All visible text and page metadata are in `index.html`. Search for square-bracketed placeholders such as `[YOUR NAME]`, `[PLACEHOLDER INTRODUCTION]`, and `[PLACEHOLDER PROJECT TITLE]`.

Important items near the top of `index.html` also need replacing:

- Change `[YOUR NAME]` everywhere.
- Change `https://YOUR-DOMAIN.example/` to the final website address.
- Check the email spelling. It is currently displayed as `jiesong [at] berkeley [dot] edu` rather than as a clickable address.
- Replace `YOUR_GOOGLE_SCHOLAR_ID` in the Google Scholar URL with the ID from your Scholar profile.

For example, to edit the contact information, search `index.html` for:

```html
<span>jiesong [at] berkeley [dot] edu</span>
```

Change only the text between `<span>` and `</span>`. The nearby HTML comment beginning `EDIT PROFILE` marks the whole profile area.

To edit the biography, find the comment beginning `EDIT INTRODUCTION` and replace the text inside the two `<p>...</p>` paragraphs underneath it.

## Add, remove, or rearrange sections

The main content in `index.html` is divided into `<section>...</section>` blocks. Job Market Paper, Work in Progress, Publications, and Teaching each have their own block.

- To remove a section, delete its entire block from the opening `<section ...>` through the matching closing `</section>`.
- To rearrange sections, move a complete section block above or below another one.
- To add a project or course, copy an existing `<article>...</article>` block within the appropriate section and replace its text.
- If you add or rename a major section, update the links inside `<nav>...</nav>` near the top of `index.html`. A link such as `href="#teaching"` jumps to the section whose opening tag contains `id="teaching"`.

## Professional headshot

The page currently uses the edited, web-optimized file:

`assets/images/headshot-web-tight.jpg`

The original photo remains separate and unchanged.

The photo is displayed at its natural height-to-width ratio and automatically uses the full width of the profile column. In `styles.css`, `.page-shell` controls the profile column width; `.headshot` should remain at `width: 100%` and `height: auto` so it scales without distortion.

To use a different photo, put it in `assets/images/` and update the `src` value on the `<img class="headshot">` element in `index.html`. Also update its `alt` text with your name.

## Curriculum Vitae

Put the CV at:

`assets/cv.pdf`

Both CV links already point to that file. Keeping the filename unchanged lets you replace the PDF later without editing the page.

## Job market paper

Put the paper at:

`assets/papers/job-market-paper.pdf`

The Paper control is intentionally disabled while the draft is unavailable. In `index.html`, replace:

```html
<span class="paper-coming" aria-disabled="true">Paper (coming soon)</span>
```

with:

```html
<a href="assets/papers/job-market-paper.pdf">Paper</a>
```

The Abstract control uses a native `<details>` element. Replace `[PLACEHOLDER ABSTRACT]` and the following instructions with the real abstract.

## Research figures

The visual summary is currently removed from the webpage. You can keep future maps and figures in `assets/images/` until you decide where to display them.

## Change the visual style

Open `styles.css`. The most useful controls are:

- At the very top, `--ink`, `--muted`, `--line`, and `--accent` set the main colors. The `--serif` and `--sans` lists control the font choices.
- `.page-shell` controls the maximum page width, the left-column width, and the gap between columns.
- `.headshot` controls the photo size and crop.
- `.introduction`, `.research-subsection`, and `.major-section` control vertical spacing.
- `.abstract-toggle summary` and `.paper-tab` control the Abstract and Paper buttons.
- Rules inside `@media (max-width: 800px)` and `@media (max-width: 580px)` control tablet and phone layouts.

Change one value at a time, save, and refresh the browser. Keep a backup before making large changes. CSS measurements commonly use `px` for exact sizes and `rem` for sizes relative to the page text.

## Preview locally

You can open `index.html` directly in a browser. For a more accurate preview, run this command from the website folder:

```powershell
python -m http.server 8000
```

Then visit `http://localhost:8000/`. Stop the preview with `Ctrl+C`.

## Publish

- **GitHub Pages:** Put these files in a repository, open **Settings > Pages**, and publish from the main branch and repository root.
- **Cloudflare Pages:** Connect the repository, leave the build command blank, and set the output directory to the repository root.

Keep the `assets` folder in the repository so the headshot, CV, paper, and figures are served locally.
