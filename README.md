# The Private Events Playbook

The ultimate guide to turning restaurant private events into a high-margin
revenue pillar — plus a live, conversion-ready example landing page you can
clone for any venue.

This repo has three self-contained pages, no build step and no dependencies:

| File | What it is |
| --- | --- |
| [`index.html`](./index.html) | **The Playbook** — the flagship guide. Makes the business case for private events and teaches the whole system: how to *package*, *design the experience*, and *convert* ads into booked events. Interactive. |
| [`example.html`](./example.html) | **The example page** — a complete private-events landing page for a made-up restaurant, *Ember & Vine*. The playbook's theory, working on a real page. |
| [`brief.html`](./brief.html) | **The submission form** — a simple form where a venue submits what it offers: rooms, how many people each holds, and the price to get started, plus contact and occasions. Wired for [Netlify Forms](https://docs.netlify.com/forms/setup/), with a *Download a copy* fallback; answers autosave in the browser. |

The pages link to each other, so a visitor can read the guide and jump
straight to a live demo of it.

## The Playbook (`index.html`)

An innovative, design-forward guide built to *feel* like the opportunity it
describes. Highlights:

- **The revenue case** — animated stat counters framing why private events are
  the highest-margin, most predictable revenue a restaurant can sell.
- **A live revenue calculator** — drag sliders (events/month, guests, spend per
  guest) and watch projected annual revenue update in real time.
- **The three levers** — *Package · Experience · Convert* — each with a deep-dive
  and a visual.
- **The conversion funnel** — an animated ad → landing page → inquiry → booked
  breakdown showing how a month of ad spend becomes real bookings.
- **The full chapter index** — the complete guide, chapter by chapter.
- Aurora-gradient background, scroll progress bar, sticky nav, and scroll reveals.

## The example page (`example.html`)

A ready-to-ship landing page for the fictional **Ember & Vine** (a wood-fired
kitchen & wine bar), demonstrating every principle from the playbook:

- **"Compose Your Evening"** — an interactive configurator: pick occasion,
  guests, package and signature moments and a live proposal panel assembles the
  matched room, inclusions and an estimated investment, then prefills the form.
- **Cinematic art direction** — an ember-particle canvas over the hero, a
  cursor-tracking spotlight, 3D tilt-on-hover room cards, and a shared warm
  colour grade so the photography reads as one art-directed set.
- A **Spaces** grid (5 rooms with photos, capacities + minimums) that lights up
  the rooms matching whatever you compose above.
- Three **package tiers** with per-guest pricing, a mosaic **gallery**, a
  testimonial, and an inquiry form wired for
  [Netlify Forms](https://docs.netlify.com/forms/setup/).
- A demo ribbon and footer that link back to the playbook.

Everything in it — venue, rooms, pricing, testimonial, contact — is invented to
illustrate the guide. Swap for a real venue's details before using it live.

## Getting started

Open either file in a browser, or serve locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000            (the Playbook)
#            http://localhost:8000/example.html (the example page)
```

## Deploying

### Netlify (recommended — the inquiry form works out of the box)

The example page's form is marked `data-netlify="true"`, so Netlify captures
submissions with no backend. Connect this repo in the Netlify dashboard, or
drag-and-drop the folder onto Netlify. `index.html` is served as the home page.

### GitHub Pages

Enable Pages under **Settings → Pages** and choose this branch with the root
folder. Note: the Netlify Forms handler will not run on GitHub Pages — the form
shows an inline success state but submissions are not captured. Wire up an
alternative backend (Formspree, Basin, a serverless function, etc.) if you host
elsewhere.

## Customizing the example for a real venue

In `example.html`, search for:

- **Brand colors** — the `:root` CSS variables (`--gold`, `--accent`, `--wine`, …)
- **Spaces** — the `SPACES` array in the `<script>` block (names, vibes,
  capacities, minimums, and which occasions each room fits)
- **Packages** — the three `.pkg` blocks (names, inclusions, pricing)
- **Copy, testimonial, footer/contact** — replace the illustrative placeholder text
- **Photography** — the hero, room cards and gallery load curated **Unsplash
  stock as placeholders** (hero URL + the `img` field in the `SPACES` array +
  the gallery `<figure>` tags). Swap those URLs for the venue's own photos. Note
  this means `example.html` needs a network connection to show its imagery.
- **Meta Pixel** — an optional `Lead` event hook is noted near the `</form>`

## A note on the numbers

Every figure in the playbook (multipliers, conversion rates, calculator output)
is an **illustrative planning benchmark**, not a guarantee — they're there to
frame the opportunity and let you plug in your own inputs.
