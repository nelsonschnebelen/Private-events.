# Private Events Landing Page

A single-page, self-contained landing site for booking private events and
celebrations — milestone dinners, holiday parties, corporate events, and more.

The page includes:

- A hero with clear calls to action
- An occasion selector (Holiday Party, Corporate, Milestone, etc.)
- A party-size **fit checker** that highlights the spaces matching a headcount
- A dynamically rendered **Spaces** grid (capacities + booking minimums)
- Three **Packages** with simple pricing tiers
- A photo gallery + testimonial section
- An inquiry form wired for [Netlify Forms](https://docs.netlify.com/forms/setup/)
- A sticky "Request a proposal" call to action

Everything lives in [`index.html`](./index.html) — HTML, CSS, and JavaScript in
one file, with no build step and no dependencies (fonts load from Google Fonts).

## Getting started

Open `index.html` in a browser, or serve it locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploying

### Netlify (recommended — the inquiry form works out of the box)

The form is marked `data-netlify="true"`, so Netlify captures submissions with
no backend. Deploy by connecting this repository in the Netlify dashboard, or
drag-and-drop the folder onto Netlify.

### GitHub Pages

Enable Pages under **Settings → Pages** and choose this branch with the root
folder. Note that the Netlify Forms handler will not run on GitHub Pages — the
form shows an inline success state but submissions are not captured. Wire up an
alternative form backend (Formspree, Basin, a serverless function, etc.) if you
host elsewhere.

## Customizing for a venue

Search `index.html` for these spots:

- **Brand colors** — the `:root` CSS variables (`--gold`, `--accent`, …)
- **Spaces** — the `SPACES` array in the `<script>` block (names, vibes,
  capacities, minimums, and which occasions each room fits)
- **Packages** — the three `.pkg` blocks (names, inclusions, pricing)
- **Copy, testimonial, and footer** — replace the illustrative placeholder text
- **Photography** — swap the `.ph-*` CSS gradient placeholders for real photos
- **Meta Pixel** — an optional `Lead` event hook is noted near the `</form>`
