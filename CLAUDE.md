# whoisbrianholl.com: Brian Holl's design portfolio

Plain static site (index.html + images/). No build step. Hosted on Netlify from this GitHub repo; every push to main deploys.

## Positioning
- Headline: "Art director. Human ideas, faster." AI is the assistant, not the art director. Every idea and final call is Brian's.
- Clients/work and roles: OneCause + Raise (lead creative since 2014), NGP VAN (lead creative), Bonterra (guides, two-pagers, paid social across its product brands), Brightmont Academy (creative director), Muse (brand redesign and style guide), Bloomerang (core design partner), Auction Packages (client), Foreign Fields (Brian's band, 75M+ streams), Casa de Copas x Warhol. EUPHORIA lives in the Other work section now. Music: Foreign Fields, Boy Bjorn (About text links to foreignfields.net and boybjorn.com).
- The $8B+ figure belongs to the OneCause platform (nonprofits raised it). Never word it as money Brian raised.
- Contact: me@whoisbrianholl.com, Milwaukee, WI.

## Look (keep it)
- Colors: forest green #173A28, cream #F3EFE7, pale sky blue, warm red #DD4B3B (tape labels, hover), acid yellow-green #EEF07A (highlight words).
- Type: Archivo expanded (Google Fonts, wdth 125) in caps for headlines; clean grotesk body. Permanent Marker for the odd hand-written accent. Brian doesn't like handwritten captions: use small Archivo caps instead (Caveat was removed).
- Details: hand-drawn BH logo, red tape-label stickers on project cards, wavy "I think we should work together" marquee, film-grain sky hero video with a bird in motion, square buttons.
- Must work on phones: no horizontal scroll, respect prefers-reduced-motion.
- Layout edges: hero box and work grid start at the section padding (72px on desktop). The stats strip is deliberately narrower and centered (Brian found full width too wide). Hero h1 has margin-left -0.065em so the H/F stems optically line up with the paragraph and buttons.
- Stats strip: light blue (#D8EBFC), no frame or divider lines (Brian dislikes heavy rules), red dash under each number. 4 across, 2x2 under 900px (.bh-stats, .bh-stat-num). Max width 1080px plus side padding clamp(0px, calc(8vw - 40px), 48px), so about 980px of content on wide screens and no extra padding on phones.
- Selected work: white section, cards are light cream panels (#F9F7F2, a tad lighter than the site cream) holding the image, name and description (.wa grid, .wa-card, .wa-body). Card art is rendered on the same #F9F7F2 so image and panel read as one. Tape labels float above the top edge (.wa-tape, absolute, top -16px), one line always (nowrap; font scales with card width via container query, clamp(10px, 2.9cqi, 14px)). Red title on hover. 3 columns on desktop, 2 under 1000px (an odd last card spans both columns and swaps to a 2:1 image), 1 under 640px. 9 cards now; keep rows full. No "All work" button (removed). Brian picked this grid over editorial rows and a mosaic.
- Email links: hero "Email me", nav "Let's talk" and the About "Let's talk" button (dark green square, kept over arrow/tape/outline options) all open mailto:me@whoisbrianholl.com.
- About: images/late-night-band-2.jpg is Brian on guitar at the far right, playing with Paper Route on Late Night with Seth Meyers (vevo watermark cropped off). Cropped and focus-graded so Brian is sharpest; he sits about 87.5% across, and the red caption arrow is positioned there (left: calc(87.5% - 33px)). Caption sits below the photo in small Archivo caps; keep text off the photo. Below it: brian-card.jpg and brian-denim.jpg, square crops of two film photos of Brian.

- "AI is my assistant" section (#how) is a bento board (.hb grid): green headline tile (headline clamp(32px, 4.6vw, 72px), about 66px at 1440 wide, sized so the tile fills without a gap; headline + paragraph kept together, gap 28px), blue "AI handles / I handle" split, yellow Faster turnarounds tile with an animated master-to-sizes SVG, white More options tile with a 3x3 sketch grid and a red ring that draws itself, red Still one of a kind tile with a spinning "Designed by a human, finished by hand" BH stamp. 4 columns on desktop, 2 under 1000px, 1 under 640px. Keep the yellow and white tiles compact (grid max 200px, SVG max 250px) so the headline tile doesn't stretch into an empty gap. All animation stops under prefers-reduced-motion.

- Motion (Brian chose both sets): one inline script at the end of body adds html.mo, never under prefers-reduced-motion or without IntersectionObserver, so with no JS the page is static. Scroll reveal: headings, stats, cards (staggered per row), bento tiles, Play images and About photos rise in; tapes slap on; stats count up and red dashes draw in. Kinetic: hero headline, paragraph and buttons slide in on load; card images parallax (about 26px); cards lift on hover and tapes wiggle; Trusted by logos are a 38s ticker with faded edges (clones are aria-hidden), paused on hover; bento tiles tilt toward the mouse. Elements get .done after their reveal so hover and tilt don't inherit stagger delays. A scroll sweep also reveals anything already on or above the screen, because fast scrolls can skip the IntersectionObserver and leave content invisible.
- Work cards are plain divs, not links (nothing to click; Brian wants no click affordance). Default cursor, hover lift and shadow stay.

## Writing rules
- No em dashes anywhere in copy.
- Short, plain, confident. No hype words.

## Still to fill (placeholders in index.html)
- LinkedIn and Instagram links currently point to #contact
- Other work section (id #play, renamed from "Play" because it includes client work): Wildewood image is images/wildewood.jpg (the old file had a dark line baked into its bottom row).
- Open questions: trim the Muse logo tagline?, cream vs white sections

## Next
- Case studies (5): OneCause + Raise, Bonterra / NGP VAN, Brightmont, Muse, Foreign Fields. Template: tape-label headline, the challenge, what I did, 6 to 10 big images, the result. One page each (e.g. /work/onecause/), linked from the home cards.

## Hosting and deploys
- GitHub: bdholl/whoisbrianholl (public, like boybjorn-site), branch main. Mirrors the boybjorn.com setup. Anything committed is public: never commit drafts, client-confidential files or the source PSD folder.
- Netlify site: whoisbrianholl (team brian-holl), https://whoisbrianholl.netlify.app, site id bd8d388f-8837-4110-afbe-d034a4d85721.
- No build command, publish directory is the repo root. Linked via a read-only "Netlify Deploy Key" on the repo plus a GitHub webhook to api.netlify.com/hooks/github, so every push to main deploys.
- Why public: Netlify's free plan blocked push builds while the repo was private ("Unrecognized Git contributor"), even with commits authored as bdholl. Public repos skip that check. Commits still use 94635561+bdholl@users.noreply.github.com (this repo's git config).
- Visitor access: public. Netlify team-login protection was turned off on 2026-11-25 when the site went live (matches boybjorn).

## Source files
- "Old Portfolio Images/" holds the original PSDs and full-size exports (about 1.9 GB). It is gitignored, as is every *.psd: GitHub rejects files over 100 MB. Export web-sized JPG/PNG into images/ and commit those.
- Work card art lives in images/work/{brand}-54.jpg (1200x960, 5:4) plus viva-21.jpg for the wide tablet slot. Each is the brand's real pieces (Muse: Thank you NLM ad, children's museum print ad, sky print ad) (cover pages or finished PNG exports) fanned on cream with soft shadows; Viva is a full-bleed poster; foreignfields-54.jpg fans three album covers (Anywhere But Where I Am, What It Cost, Take Cover) cut from the vinyl mockups in ~/Sites/foreignfields-site/images; EUPHORIA's poster is images/euphoria-poster.jpg in Other work; Bloomerang fans three ads from the Bloomerang/ folder (screenshots, edges trimmed 2px). Brand source folders (NGP VAN, Bonterra, Brightmont, Muse, Auction Packages, ~11 GB) sit in the project root and are gitignored along with *.pdf, *.psd, *.ai, *.indd.
- Copy facts from the source folders: NGP VAN 13 guides/playbooks (PAC Playbook, Win Your Local Election, VANual, MiniVANual, Quick Start, GOTV, Moment-based fundraising, Complete guide to political fundraising, Coalition, Volunteer Recruitment, Tectonica distributed organizing, 2026 Election Prep Checklist, 50 Fundraising Ideas) plus Navigator AI launch socials; Bonterra 3 long-form guides + 7 product two-pagers (EveryAction, Network for Good, CyberGrants, Deed, DonorDrive, Que, OneCause).
- The "-portfolio" files are finished collages with baked-in tape labels and text (Raise's label contains an em dash). Prefer individual pieces for the site.

## Domain (careful)
- LIVE since 2026-11-25: https://whoisbrianholl.com on Netlify. Let's Encrypt certificate (covers whoisbrianholl.com and www, auto-renewed by Netlify), force_ssl on, so http and www redirect to https://whoisbrianholl.com.
- Netlify site has custom_domain whoisbrianholl.com with alias www.whoisbrianholl.com (same setup as boybjorn). DNS is managed in Squarespace Domains (nameservers ns-cloud-e1..e4.googledomains.com). Current records: A @ 75.2.60.5 and CNAME www whoisbrianholl.netlify.app (custom records). They replaced the Squarespace Defaults preset, which was deleted (4 A records 198.185.159.144/145 and 198.49.23.144/145, CNAME www ext-sq.squarespace.com, plus an HTTPS record pointing at Squarespace). Keep the Squarespace Domain Connect, Domain Connect to Google and Google Workspace presets. The Squarespace website plan ends Dec 1, 2026.
- Email records to keep exactly as they are: 5 Google MX (aspmx.l.google.com priority 1, alt1/alt2 priority 5, alt3/alt4 priority 10) and 2 google-site-verification TXT records.
- When pointing the domain at Netlify, change only the A record and www record. Never touch MX or TXT records: they carry me@whoisbrianholl.com email.
