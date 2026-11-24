# whoisbrianholl.com: Brian Holl's design portfolio

Plain static site (index.html + images/). No build step. Hosted on Netlify from this GitHub repo; every push to main deploys.

## Positioning
- Headline: "Art director. Human ideas, faster." AI is the assistant, not the art director. Every idea and final call is Brian's.
- Clients/work: OneCause + Raise (since 2014), Bonterra + NGP VAN, Bloomerang, Brightmont Academy, Muse, Auction Packages, EUPHORIA, Casa de Copas x Warhol. Music: Foreign Fields (75M+ streams), Boy Bjorn.
- The $8B+ figure belongs to the OneCause platform (nonprofits raised it). Never word it as money Brian raised.
- Contact: me@whoisbrianholl.com, Milwaukee, WI.

## Look (keep it)
- Colors: forest green #173A28, cream #F3EFE7, pale sky blue, warm red #DD4B3B (tape labels, hover), acid yellow-green #EEF07A (highlight words).
- Type: Archivo expanded (Google Fonts, wdth 125) in caps for headlines; clean grotesk body. Permanent Marker / Caveat for hand-written notes.
- Details: hand-drawn BH logo, red tape-label stickers on project cards, wavy "I think we should work together" marquee, film-grain sky hero video with a bird in motion, square buttons.
- Must work on phones: no horizontal scroll, respect prefers-reduced-motion.

## Writing rules
- No em dashes anywhere in copy.
- Short, plain, confident. No hype words.

## Still to fill (placeholders in index.html)
- Bonterra + NGP VAN card image: [Guide covers + ad set grid + Navigator logo]
- Brightmont card image: [Brightmont catalog + tri-folds], plus "[ADD A RESULT]"
- About: "[ONE MORE LINE ABOUT YOU]", photos "[A photo of you working]" and "[Your desk, sketches or studio]"
- LinkedIn and Instagram links currently point to #contact
- Open questions: which guitarist Brian is in the late-night TV photo (to aim the arrow), trim the Muse logo tagline?, cream vs white sections

## Next
- Case studies (5): OneCause + Raise, Bonterra / NGP VAN, Brightmont, Muse, Foreign Fields. Template: tape-label headline, the challenge, what I did, 6 to 10 big images, the result. One page each (e.g. /work/onecause/), linked from the home cards.

## Hosting and deploys
- GitHub: bdholl/whoisbrianholl (private), branch main. Mirrors the boybjorn.com setup.
- Netlify site: whoisbrianholl (team brian-holl), https://whoisbrianholl.netlify.app, site id bd8d388f-8837-4110-afbe-d034a4d85721.
- No build command, publish directory is the repo root. Linked via a read-only "Netlify Deploy Key" on the repo plus a GitHub webhook to api.netlify.com/hooks/github, so every push to main deploys.
- Commits must be authored as bdholl (this repo's git config uses 94635561+bdholl@users.noreply.github.com). Netlify's free plan blocks builds of private-repo commits from unrecognized authors, such as the Mac's default hostname email.
- Visitor access: Netlify "team login" protection is ON (new-site default), so the netlify.app URL only works when logged in to Netlify. boybjorn has it off. Turn it off (Site configuration > Access & security > Visitor access) before connecting the domain.

## Source files
- "Old Portfolio Images/" holds the original PSDs and full-size exports (about 1.9 GB). It is gitignored, as is every *.psd: GitHub rejects files over 100 MB. Export web-sized JPG/PNG into images/ and commit those.
- The "-portfolio" files are finished collages with baked-in tape labels and text (Raise's label contains an em dash). Prefer individual pieces for the site.

## Domain (careful)
- whoisbrianholl.com currently on Squarespace; the Squarespace website plan ends Dec 1, 2026.
- When pointing the domain at Netlify, change only the A record and www record. Never touch MX or TXT records: they carry me@whoisbrianholl.com email.
