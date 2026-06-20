# Rebuild Spec: michaelaugros.com (v2)

**Status:** proposed. Supersedes the v1 "speaker booking funnel."
**Date:** 2026-06-20
**Author:** Peter (with Claude). Pending Michael's nod on purpose & positioning.

---

## 1. Why we're rebuilding

The v1 site is built around **"Invite Michael to Speak."** Michael read it and rejected that
premise (not the design, he liked the look and most of the copy). His own words:

> "I am not really free to speak... I don't want to be chasing the lecture circuit, or doing lots
> of interviews, they are not a medium for making available the things I want to make available,
> but are more like advertisement. What I want to do is in-person instruction... I also want to
> make things available via video or online publishing. I'm pursuing the writing angle with
> Substack... the video angle with TAC, if an organization with bigger reach were to invite me to
> produce videos in a way that could accommodate my teaching job, that would be great
> (e.g., Peterson Academy)."

So booking is **not** the goal. The goals, in his words, are: **make his ideas available** (writing +
video), and **land a video/online partnership that fits around his teaching job.**

## 2. North star

> **One person at a Peterson-Academy-type organization clicks one link and comes away thinking:
> "This man is the real thing, and I want to build something with him."**

Every element earns its place against that test or it's cut. Speaking footage stays, but as
*proof he can hold a room* (credibility), not as a booking funnel.

Why the site still matters even though Michael doubted it: Peterson Academy and similar are
**invitation-only, there is no application.** You get invited by being visible (Substack + video),
vouched-for (a bridge like Matt Fradd / Pints with Aquinas), and **verifiable**, and the website is
what verifies calibre when someone checks him out. It's the closer, not the lead.

## 3. Audience & positioning

**Audience:** thoughtful people who suspect the deepest questions have real answers and want them
taken seriously, *both* the searching newcomer *and* the already-Catholic reader hungry for depth.
The uniting trait is **seriousness, not expertise level.**

**Positioning:** *Depth, made clear, for people who are serious.* Michael talks about whatever deep
idea he wants, at full depth, while staying followable by a smart beginner, which is his documented
gift. This is **not** "philosophy for beginners" and **not** "academic philosophy."

> Open decision for Michael to confirm: does this framing fit? It's built so he never has to dumb
> anything down.

## 4. What the site does (three jobs)

1. **Landing page, "Who is Michael Augros."** A credibility-grade introduction: who he is, the
   quality of his mind, evidence he can hold a room (video).
2. **Engine for his work, feed Substack, surface his output.** Drive subscribers; auto-mirror his
   latest Substack posts; house the podcast. The site amplifies Substack, it does not ask him to
   publish twice.
3. **CV + a quiet "work together."** Downloadable CV, credentials, and a low-key invitation (in-person
   teaching, video/online collaboration), a footnote, not the headline. No "book me" funnel.

## 5. Information architecture (repointed)

Single-page-forward with anchor nav, as today. Sections, top to bottom:

| Section | v1 (now) | v2 (proposed) |
|---|---|---|
| **Hero** | "Invite Michael to Speak" CTA | Positioning line + **primary CTA: Subscribe on Substack**; secondary: "Watch" |
| **About** | bio | keep, lightly retuned to the "depth made clear" posture |
| **Ideas / Watch** | "Speaking" (booking) | Renamed. Video series + clips as **proof of calibre**; talk topics reframed as *themes he explores*, not a booking menu |
| **Writing / Substack** | static "publications" | **Live feed of latest Substack posts (RSS)** + Subscribe CTA + books |
| **Podcast** | (new) | The Michael + Peter conversation; audio embeds (Substack-hosted) |
| **Ask Michael** | (new) | Question box that fuels content |
| **Credentials + CV** | keep | keep; CV is a drop-in PDF Michael can replace himself |
| **Work together** | "Contact / Booking" | Softened: collaboration + teaching inquiry, low-key |

**Format is fixed; content flexes to length** (templated, long bio or short bio both look right).

## 6. Self-edit / CMS: the core new capability

**Requirement:** Michael signs in (a "secret chord") and controls the message himself, edit copy,
swap photos, replace the CV PDF, add/remove links, add podcast episodes, **without touching code**,
and *feel* ownership of the message. Format never breaks; it just reflows to his lengths.

**Why this matters beyond convenience:** the point is that **the message is his, not Peter's.** Even
if he edits rarely, the control has to be real and visible to him.

**Architecture:** static site generator + **git-based CMS**. Content lives in editable files
(markdown/JSON) in the repo; Michael edits through a friendly admin screen at `/admin`; saving commits
to git; the host (Netlify / Cloudflare Pages) rebuilds automatically. Owned, fast, ~free.

**Editable through the admin UI (no code):**
- All headline + body copy (per section)
- Photos (upload / replace, auto-optimized)
- **CV**, drop a new PDF, it replaces the old
- Links (Substack, books, social, video)
- Structured lists: video clips, themes/topics, testimonials, books, podcast episodes
- The "Ask Michael" curated Q&A (optional, later)

### Stack decision: ONE thing to choose (see §11)

| Option | Editor login | Editing feel | Cost | Trade-off |
|---|---|---|---|---|
| **A. Astro + Sveltia/Decap CMS** (recommended for owned+free) | GitHub account | Clean form-based admin | Free | Michael needs a GitHub login (mild friction) |
| **B. Astro + TinaCMS** (recommended for friendliest UX) | Email-based | In-context, click-the-text-to-edit | Free tier, then paid | Slightly more setup; auth via TinaCloud |

Both keep the site static and let Michael self-edit. The real difference is **his login experience.**
Recommendation: **B (TinaCMS)** if making Michael comfortable signing in is the priority (it is, he
must *feel* in control); **A (Sveltia)** if maximum ownership/zero-cost matters more and a GitHub
login is acceptable.

## 7. Substack integration

- **Auto-mirror latest posts** via Substack's RSS feed, pulled at build time (and/or client-side),
  so the site always looks alive with zero extra work for Michael.
- **Subscribe** is a primary CTA (hero + Writing section + footer), replaces "Invite to Speak" as
  the spine. Growing the owned email list is the actual goal and the asset he brings to any partner.
- **Podcast lives inside Substack** (native audio hosting), episodes embed on the site's Podcast
  section. One feed, one list, words + audio together.

## 8. Podcast

- Format: **Michael + Peter**, ~10 min conversation on each essay. Zoom + good mics. Audio-only to
  start (no video editing, respects Michael's hesitancy). Add video later only if it has legs.
- Pipeline: **one recording → Substack essay + podcast episode** (+ optional clips later). Michael
  only thinks/writes/talks; everything downstream is production (Peter / editor / AI tooling).
- Guardrail: Peter is the *foil* (asks what the audience is thinking), not a co-host with his own
  thesis. The ideas stay Michael's.

## 9. "Ask Michael" feature

- A simple question box → emails Peter + Michael (no backend; Netlify Forms or Formspree).
- Jobs: audience feels seen; endless content prompts; best questions become essays/episodes.
- Later (optional): a curated public Q&A section Michael edits via the CMS.

## 10. What carries over vs. changes

**Carries over:** visual design/typography (Cormorant + Inter), the two book entries, real video
embeds (EWTN, Patrick Coffin, *The Mind & the Machine* Ep. 10), testimonials (generic, no student
names, keep this rule), credentials, photos.

**Changes:** the spine (Subscribe, not Book); Speaking → Ideas/Watch (proof, not funnel); add
Substack feed, Podcast, Ask Michael; everything becomes CMS-editable; contact softened to
"work together."

## 11. Open decisions (need answers before/while building)

1. **CMS choice, §6:** TinaCMS (friendliest login) vs. Sveltia/Decap (most owned/free). *Peter to pick.*
2. **Positioning line, §3:** Michael confirms "depth made clear for the serious."
3. **Domain:** michaelaugros.com? (confirm + set `og:url`, social-share image).
4. **Substack URL:** not live until Fall 2026, feed wiring waits on it; build the slot now.
5. **CV PDF:** still being updated by Michael; ships as drop-in once delivered.
6. **Host:** Netlify vs. Cloudflare Pages (both fine; pick by CMS auth convenience).

## 12. Non-goals (explicit)

- No "book me / lecture circuit" funnel.
- No custom backend / database / user accounts (audience-side).
- No second place Michael has to publish (Substack is the source of truth for writing).
- No re-uploading others' video without permission (embeds only, per the v1 note).

## 13. Build phases

1. **Repoint copy & IA** on the current static site (fast, low-risk, shows Michael the new direction).
2. **Introduce the SSG + CMS** (Astro + chosen CMS); migrate content into editable collections.
3. **Wire Substack RSS feed + Subscribe CTAs.**
4. **Add Podcast section + Ask Michael form.**
5. **Self-edit handoff:** short Loom/walkthrough so Michael can log in and change something himself.

Phase 1 is showable to Michael on its own, the best way to win his buy-in is to let him *see* the
repointed site, not just read this spec.
