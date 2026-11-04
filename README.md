# EICF Search

**The shortest path to an Emory core.**

Live at **[eicfsearch.apphatchery.org](https://eicfsearch.apphatchery.org)**

EICF Search is a conversational guide to the [Emory Integrated Core Facilities (EICF)](https://www.cores.emory.edu/eicf/). Researchers can ask in their own words, such as "Where can I get two-photon imaging?" or "I need germ-free mice for a microbiome study," and get pointed to the right core, instrument, and contact, without needing to know the facility's name or acronym first.

Built by [AppHatchery](https://apphatchery.org) with Emory Integrated Core Facilities.

## Why it exists

Emory has more than 20 integrated cores, each with its own page, services, and acronym. Researchers think in questions; core catalogs are organized by facility. EICF Search bridges that gap by letting people describe what they need and get routed to the core that offers it.

## What the site does

- **Hosts the EICF Search chatbot.** The assistant runs on [Chatbase](https://www.chatbase.co) and is embedded in the page, so visitors can start asking questions right away.
- **Brands the experience for Emory.** The page carries the Emory School of Medicine and EICF logo, the EICF Search mark, and an AppHatchery credit.
- **Collects feedback.** A "Help us improve" link opens an Emory Qualtrics survey in a new tab.
- **Interactive background.** The page background is a wall of real EICF core acronyms. Hovering one shows the core's full name; clicking one copies a ready-made question about that core to paste into the chat.
- **Light and dark modes.** A toggle in the top-right corner switches themes. First-time visitors get their device's setting, and the choice is remembered.
- **Collapsible side panel.** On desktop, the side panel folds into a slim strip of logos, so the chat gets more room. It also collapses automatically when someone clicks into the chat, and stays open if they reopen it.
- **Works on phones.** On small screens the page switches to a slim header with the chat filling the screen. The survey link, logos, and credits sit below.
- **Scales to large screens.** Margins, spacing, and the chat window grow with the screen size.
- **Fallback chat view.** The page embeds Chatbase's full chat page. If it ever fails to load, a "Chat not loading? Try the simple view" link switches to Chatbase's officially supported chat window, and the page switches on its own if the chat hasn't loaded after 15 seconds.

## How it's built

A single static page with no build step or dependencies:

- Plain HTML, CSS, and JavaScript in `index.html`
- Fonts from Google Fonts (Fraunces, Instrument Sans, Barlow Condensed)
- The chatbot is embedded in an iframe from Chatbase
- Hosted on GitHub Pages with a custom subdomain

The page stores three small preferences in the visitor's browser (theme, panel collapsed or open, chat view). No personal data is collected by the page itself; conversations happen inside the Chatbase embed and survey responses go to Qualtrics.

## Files

```
index.html     The whole site: layout, styles, and scripts
CNAME          Tells GitHub Pages to serve the site at eicfsearch.apphatchery.org
README.md      This file
assets/        Logos and icons
  favicon-32.png, favicon-180.png, favicon-512.png   EICF Search mark (browser tab, home screen, link previews)
  emory-eicf-logo-white.png / -navy.png              Emory School of Medicine + EICF logo (dark / light mode)
  lockup-white-* / lockup-navy-*                     The same logo split in two, for the collapsed side panel
  apphatchery-logo.png / -logo-light.png             AppHatchery logo (light / dark backgrounds)
  apphatchery-icon.png / -icon-color.png             AppHatchery icon for the collapsed side panel
```

## Common updates

All edits are made in `index.html`. After committing, GitHub Pages republishes the site within a few minutes; do a hard refresh to see changes.

| To change | Look for |
| --- | --- |
| The survey link | `som.qualtrics.emory.edu` (appears twice: desktop panel and phone layout) |
| The chatbot | `zDt_jEphc3lenROqsPX3S` (the Chatbase agent ID) |
| Make the simple chat view the default | Replace the `/help` address in the `botFrame` iframe with `https://www.chatbase.co/chatbot-iframe/zDt_jEphc3lenROqsPX3S` |
| The tagline | `The shortest path to an Emory core.` |
| The list of background acronyms | `const CORES=` in the script at the bottom of the page |
| Copyright year | `© 2026 Emory University` |

## Hosting

- **GitHub Pages:** Settings > Pages, deploy from the `main` branch, `/ (root)` folder.
- **Custom domain:** `eicfsearch.apphatchery.org`, set in Settings > Pages, with **Enforce HTTPS** on.
- **DNS** (managed in Squarespace for apphatchery.org): one CNAME record, `eicfsearch` pointing to the GitHub Pages host for this repository's account (`<account>.github.io`). No other apphatchery.org records are involved.
- **Chatbase:** if the agent restricts allowed domains, `eicfsearch.apphatchery.org` must be on the list.

## Credits

Designed and built by [AppHatchery](https://apphatchery.org), an interdisciplinary digital health incubator in the Georgia CTSA program at Emory University, in partnership with Emory Integrated Core Facilities.

© 2026 Emory University
