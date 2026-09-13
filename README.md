# Vijayas Healthcare & Medicals — website

Plain static HTML/CSS, no build step, no dependencies. `index.html` is the whole site.
Designed to be pushed straight to Cloudflare Pages with **build command: none**,
**output directory: `/`**.

## What's on the page right now

Only facts confirmed in `../CLAUDE.md` and the live Zoho org record:
business name, proprietor, address, GSTIN, drug licence numbers, the four supplier
brands, and the account phone number from Zoho (`+91 63808 16260`) — **that last one
needs Suresh to confirm it's the number he wants published** (see below).

## Still needed before this goes live

- **Confirm the public phone number.** Right now it's the number on the Zoho account.
  Might be his personal mobile rather than a shop line — ask him.
- **Business hours.** Not stated anywhere in the project files, so the page currently
  just says "call ahead." Add real hours once he confirms them.
- **A tagline / "since [year]" isn't included on purpose** — GST registration (2017) and
  actual founding aren't confirmed to be the same year (see the open question in
  `../CLAUDE.md` about the six-month gap before the first invoice). Don't add a founding
  year without asking him directly.
- **Logo / photos.** None exist yet. The header currently uses a plain "V" mark.
- **WhatsApp button** — deliberately left off. `../CLAUDE.md` notes WhatsApp Business
  isn't verified yet (OTP has to go to Suresh in person). Add a `wa.me` link once that's done.
- **Domain.** `vijayas.in` is mid-registration and blocked on the brother's own
  MeriPehchaan/eKYC step (see project notes). Until it resolves, deploy to the free
  `*.pages.dev` subdomain Cloudflare gives every Pages project — the DNS/domain step is
  separate from the deploy step and doesn't block it.

## Deploying — what I need from you

I can't push to GitHub or connect Cloudflare from here without credentials:

1. **GitHub**: `gh auth login` isn't authenticated in this environment. Either run it
   yourself in a terminal, or give me a repo to push to (I can create one once `gh` is
   authenticated as you).
2. **Cloudflare**: no `wrangler` login/API token available here either. Cloudflare Pages
   can deploy straight from a GitHub repo (connect it in the Cloudflare dashboard, no
   token needed) — that's the simplest path and needs no credential in my hands at all,
   just you clicking "Connect to Git" once the repo exists.

So the fastest route: I push this to a new GitHub repo (once `gh` is logged in), you
connect that repo to Cloudflare Pages in their dashboard (a few clicks, no CLI), and
every future `git push` auto-deploys.
