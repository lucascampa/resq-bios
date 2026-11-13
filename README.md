# resq-bios

A one-page site with the ResQ Intelligence team's professional bios. People reach it by scanning the QR code on the closing slide of our pitch.

**Live at:** https://lucascampa.github.io/resq-bios/
**Repo:** https://github.com/lucascampa/resq-bios (public, because free GitHub Pages needs it)

ResQ Intelligence builds disaster-site rescue robotics: a ground "mothership" robot crosses collapsed-building debris, launches smaller units into gaps people and dogs can't reach, drops relay modules that keep the site connected, and opens a two-way line between a trapped survivor and the rescue team. Tagline: **Search. Connect. Save lives.**

## Status

- Lucas's card is done and live.
- Julie, Rasaq and Rasul don't have cards yet. Each sends their bio and it gets added by hand (see "Adding a bio").

## Who it's for

The page is presented in the context of a master's capstone project, and it's meant to outlast the presentation. It's a professional bio of each team member, with room for far more detail than the pitch's time limit allows. It should leave people with something to remember each of us by. It will be available for about two years.

**Pitch audience:** investors, judges and faculty who just watched the pitch. They scan the QR code on their phone, usually in the room or right after. They want to know who the team is, why each person is credible, and how to reach us.

**Long-term audience:** people inside organizations with the power to hire us. Lucas's case is the clearest one: he's a software engineer, and the page should help a hiring-capable reader see what he can do and get in touch.

So the page must:

- Work on a phone first (360px wide and up), then scale up to desktop.
- Load fast on venue Wi-Fi or cellular: compressed images, no heavy libraries.
- Read quickly in its collapsed state, with the full story one tap away.

## Page structure

One page, in this order:

1. **Header.** ResQ Intelligence logo and name, the tagline "Search. Connect. Save lives.", and the line "Meet the Team".
2. **Team.** One card per person, stacked in a single column at every screen width (centered, about 760px wide on desktop).
3. **Footer.** "© 2026 Lucas Campagnaro". No reference to the capstone, ResQ or the university.

No nav menu, no cookie banner, no analytics, no contact form, no separate contact section. Each person's contact links live inside their own card.

## Bio cards

Each card, top to bottom:

1. Photo (square, cropped to a circle, about 160px)
2. Name and role
3. **Keywords:** small outlined pills in the amber accent (about five per person)
4. **Short version**, always visible: a bold one-sentence hook, a short paragraph, and a closing invitation. Most readers won't expand, so the invitation lives here.
5. **"More about me" button**, which expands the full version. It reads "Show less" when open.
6. **Expanded version:** the long-form bio, a few paragraphs in first person.
7. **Links:** LinkedIn and GitHub icons, then the email on the row below with an envelope icon and a small, dimmed copy button to its right.

The keywords, short version and links stay visible whether the card is collapsed or expanded. The links sit at the bottom of the card, below the expanded text.

How it's built:

- The expansion is a native `<details>` / `<summary>` element, with a tap target at least 44px tall and a chevron.
- The one piece of JavaScript is a small inline script that powers the copy-email button. It uses the clipboard API, with a fallback.
- Icons are in `images/icons/`. LinkedIn and GitHub use the image files, and the envelope and copy icons are inline SVG.

Links appear only if that person agrees to them. Spell out acronyms where it helps the reader (judges flagged too many acronyms in the pitch).

## Adding a bio

Each teammate sends a bio document split into three parts, in the format of Lucas's (`lucas bio.md`, kept local):

- **Keywords:** a short list for the pills
- **Short:** the always-visible version, with the hook in bold and a closing invitation
- **Expanded:** the long-form version

Along with that they send a photo and the links they want shown (LinkedIn, GitHub, email). Names and roles come from the pitch deck's Management Team slide. Never write bio details the person hasn't provided.

### Julie Pavlova
- **Role:** Product & Business
- **From the pitch:** eight years of business ownership and experience in the drone detection industry.
- **Bio, photo and links:** `[TODO]`

### Lucas Campagnaro
- **Role:** Technology, R&D
- **Photo:** `images/lucas.png`
- **Keywords:** Applied AI · Machine Learning · Software Engineering · Python · Operations Research
- **Bio and links:** done, on the page

### Rasaq Sule-Odu
- **Role:** Marketing Strategy
- **From the pitch:** electrical engineering, and IT security and DevSecOps (development, security and operations).
- **Bio, photo and links:** `[TODO]`

### Rasul Abdul-Salaam
- **Role:** Finance & Operations
- **From the pitch:** property and operations analysis, and cybersecurity and information technology.
- **Bio, photo and links:** `[TODO]`

## Look and tone

Match the pitch deck so the page feels like the slide that sent people there:

- **Background:** dark navy `#0A1B2C`
- **Accent:** amber `#F2C465` (keyword pills, links, role line, thin dividers)
- **Text:** off-white `#F7F7F5` for headings, light blue-gray `#C9D5DF` for body
- **Fonts:** Exo 2 for headings, Inter for body (Google Fonts), with system sans-serif fallbacks
- Keep body text at 16px or larger and check contrast (WCAG AA). The copy button is deliberately dimmer than the rest, so check it too.

Tone: confident, plain and human. First person in bios. No buzzwords, no hype, and no claims we can't back up.

## Files

```
resq-bios/
├── index.html
├── styles.css
├── README.md
├── CLAUDE.md
├── .gitignore
└── images/
    ├── logo.png
    ├── lucas.png        # team photos (aim for ≤200 KB each)
    └── icons/
        ├── github.png
        └── linkedin.png
```

Bios are plain HTML in `index.html`. There is no backend, no sign-in and no editing on the live page.

Give every photo `alt` text with the person's name, and keep `<title>`, the meta description and the Open Graph image set so the link previews well if someone shares it.

**Local only, not in the public repo:** `lucas bio.md` (the bio draft) and the unused `images/bg*.png` files. They're listed in `.gitignore`. This README and `CLAUDE.md` are in the repo.

## Publishing

The site is served by GitHub Pages from the `main` branch, folder `/ (root)`. To update it, edit the files, commit and push to `main`. The site redeploys in a minute or two.

Keep the repo name, username and branch the same, or the URL breaks. Content can change freely; the URL can't.

If the repo is ever made private on a free account, the Pages site goes offline.

## The QR code

1. Open the live URL on a phone and check it before making the QR code.
2. Make a **static** QR code that encodes that exact URL. Avoid "dynamic" QR services, which route through their own short link and can expire or add ads.
3. Export it as PNG or SVG with a white quiet-zone border, place it in the QR slot on the closing slide, and test-scan it from the projected size.

## Before sharing

- [ ] Every `[TODO]` is filled or removed
- [ ] Each teammate approved their own bio, photo and links
- [ ] Photos compressed (`lucas.png` is about 218 KB, a little over the 200 KB goal)
- [ ] Page checked on an iPhone and an Android phone, including "More about me" and the copy button
- [ ] QR code scans from the slide and opens the live page
