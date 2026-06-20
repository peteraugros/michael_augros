# Michael Augros: site

Static site for Michael Augros, philosopher, teacher, and writer.
No build step, no dependencies. Just HTML/CSS/JS.

The full strategy and rationale live in [`docs/rebuild-spec.md`](docs/rebuild-spec.md).
Short version: this is **not** a speaker-booking funnel. It's a credibility-grade **hub for
Michael's ideas** whose jobs are (1) introduce him, (2) feed and amplify his Substack, and
(3) serve as the professional calling card someone (Matt Fradd, a Peterson Academy scout)
finds when they look him up. The spine is **Subscribe**, not "book me."

## Run it locally

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

(Open `index.html` directly and the YouTube embeds stay blank, they need http(s). Use the server.)

## Structure

```
index.html              # the whole page (anchor-nav sections)
css/styles.css          # all styles
js/main.js              # mobile nav + footer year
assets/img/             # photos
assets/docs/            # CV (PDF), drop here when delivered
docs/rebuild-spec.md    # vision, IA, CMS plan, open decisions
```

Sections, top to bottom: Hero → About → Ideas (videos, themes, testimonials = proof of calibre)
→ Writing (Substack subscribe + book list) → Podcast → Credentials (CV download) → Connect
(Ask Michael + a quiet "work together"). The **Subscribe** CTA lives in the header, hero,
Writing, Podcast, and footer.

## Roadmap

This is **Phase 1**: the existing static page repointed to the new direction (showable to Michael).
Next phases (see the spec): move to **Astro + TinaCMS** so Michael can sign in and self-edit
everything, wire the **Substack RSS feed**, and connect the **Ask Michael** form.

## Pre-launch checklist

- [ ] Michael blesses the new direction (show him this Phase 1).
- [ ] Confirm positioning, bio, talk-theme framing, and credentials with Michael.
- [ ] Add the real **Substack URL** when it launches (Fall 2026), replaces the `#` and `#writing`
      placeholders on every Subscribe button + the hero CTA.
- [ ] Wire the **Ask Michael** form to a service (Formspree / Netlify Forms).
- [ ] Drop the real **CV** at `assets/docs/michael-augros-cv.pdf`.
- [ ] Confirm book purchase links.
- [ ] Set `og:url` and add a real social-share image.
- [ ] Optimize the hero/about photos (currently 1–2.6 MB each).
- [ ] Create a YouTube channel that is actually Michael's, as the home for future clips.

## Note on video ownership

Michael does not currently own a YouTube channel, his videos live on Thomas Aquinas College,
EWTN, and the Patrick Coffin Show. Embedding their players is fine; re-uploading/clipping their
footage to a channel of his own needs permission from each source.

## Deploy

Any static host works: Netlify, Vercel, GitHub Pages, Cloudflare Pages. For Phase 2 (TinaCMS),
Netlify or Cloudflare Pages is the natural pairing.
