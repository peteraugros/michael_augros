# Michael Augros — site

Static single-page site for Michael Augros — philosopher, speaker, author.
No build step, no dependencies. Just HTML/CSS/JS.

## Run it locally

Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Structure

```
index.html              # the whole page (anchor-nav sections)
css/styles.css          # all styles
js/main.js              # mobile nav + footer year
assets/img/             # photos
assets/docs/            # CV (PDF) + testimonials source
```

Sections, top to bottom: Hero → About → Speaking (videos, talk topics, testimonials)
→ Writing → Credentials (CV download) → Contact/Booking. The "Invite Michael to Speak"
CTA lives in the header, hero, Speaking section, and footer.

## What's real vs. placeholder

Search the source for these markers:

- **`DRAFT`** — content I drafted from public info (bio, positioning line, talk titles,
  credentials). Confirm/replace with Michael's approved wording.
- **`TODO`** — things to wire up before launch (see checklist below).
- **`VIDEO_ID_1` / `VIDEO_ID_2`** — placeholder video embeds. One real embed is live in
  the Speaking section (EWTN "Who Designed the Designer?", id `V7lavrqdrMY`).
- **`CONTACT_EMAIL`** — replace with the real booking email.

## Pre-launch checklist

- [x] Booking email set to `[redacted]` (his reliable personal address; the
      school address `maugros@thomasaquinas.edu` is unreliable — do not surface it).
- [ ] Wire the contact form to a service (Formspree, Netlify Forms, or Google Form embed).
- [ ] Drop the real CV at `assets/docs/michael-augros-cv.pdf` (Michael is updating it).
- [x] Positioning one-liner approved by Michael (hero lede).
- [ ] Confirm bio, talk titles, and credentials with Michael.
- [ ] Add the Substack URL when it launches (Fall 2026); footer currently says "launching Fall 2026".
- [ ] Swap `VIDEO_ID_1/2` for real clip IDs (ideally from Michael's *own* channel — see note).
- [ ] Confirm book purchase links (The Immortal in You link is a placeholder `#`).
- [ ] Set `og:url` and add a real social-share image.
- [ ] Optimize the hero/about photos (currently 1–2.6 MB each).

## Note on video ownership

Michael does not currently own a YouTube channel — his videos live on Thomas Aquinas
College, EWTN, Patrick Coffin Show, and FORMED. Embedding their videos is fine (the
embeds just point at their players). Re-uploading/clipping their footage to a channel of
his own requires permission from each source. The highest-leverage early move is creating
a channel that is actually his, as the home for future clips.

## Deploy

Any static host works: Netlify, Vercel, GitHub Pages, Cloudflare Pages. Drag-and-drop the
folder, or connect a git repo. No configuration needed.
