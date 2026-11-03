# EICF Search

One-page site for EICF Search: the Chatbase bot embedded in an Emory-branded page, with light and dark modes. Built by AppHatchery.

## Files
- `index.html`: the whole page (styles and scripts included)
- `assets/`: logos and icons used by the page

## Before you publish
- "Suggest a name for our tool" links to `SUGGEST_URL`. Open `index.html`, search for `SUGGEST_URL` (it appears twice), and replace both with your form link.
- In Chatbase, if the agent restricts allowed domains, add your GitHub Pages address and your custom domain.

## Publish on GitHub Pages
1. Create a public repository (for example `eicf-search`).
2. Upload `index.html`, `README.md`, and the `assets` folder to the root of the `main` branch.
3. Go to **Settings > Pages**. Set Source to **Deploy from a branch**, Branch **main**, folder **/ (root)**, and save.
4. After a minute the site is live at `https://<org>.github.io/eicf-search/`. Open it and ask the bot a question to confirm the chat loads.

## Add a custom domain
1. In your DNS provider, add a **CNAME** record for the subdomain (for example `search.yourdomain.org`) pointing to `<org>.github.io`.
   - For a root domain with no subdomain, add **A** records to 185.199.108.153, 185.199.109.153, 185.199.110.153 and 185.199.111.153 instead.
2. In **Settings > Pages**, enter the domain under "Custom domain" and save. GitHub adds a `CNAME` file for you.
3. When the DNS check passes, tick **Enforce HTTPS**.

## If the chat ever stops loading
The page embeds Chatbase's full chat page (`/help`). Chatbase officially supports embedding its simpler chat window, so visitors can switch to it with the link at the bottom of the page. To make the simple window the default for everyone, replace the `/help` address in the `botFrame` iframe in `index.html` with `https://www.chatbase.co/chatbot-iframe/zDt_jEphc3lenROqsPX3S`.
