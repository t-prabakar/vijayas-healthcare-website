# Vijayas Healthcare & Medicals — website

Plain static HTML/CSS, no build step, no dependencies. `index.html` is the whole site.
Deploys as a Cloudflare Worker with static assets — see `wrangler.jsonc`.

## Live

- **https://vijayas.in** and **https://www.vijayas.in** — custom domains, both bound
  directly to the Worker via the Cloudflare API (`workers/domains` endpoint), not
  through `wrangler.jsonc`. DNS is hosted on Cloudflare (moved from DomainIndia
  2026-09-13); DomainIndia stays the registrar.
- **https://vijayas-healthcare-website.tk-prabakar.workers.dev** — the underlying
  `*.workers.dev` URL, still works, not meant to be shared publicly now that the real
  domain resolves.
- Auto-deploys from `main` on every push (Cloudflare dashboard → Connect to Git).
  Feature-branch preview builds are enabled.

## What's on the page

Facts confirmed in `../CLAUDE.md`, the live Zoho org record, and what Suresh has
given directly: business name, proprietor, address, GSTIN, drug licence numbers, the
four supplier brands, phone number, WhatsApp, and hours (Mon–Fri 10:00–20:30, Sat
10:00–12:00, closed Sundays).

## Still open

- **A tagline / "since [year]" is left off on purpose** — GST registration (2017) and
  actual founding aren't confirmed to be the same year (see the open question in
  `../CLAUDE.md` about the six-month gap before the first invoice). Don't add a
  founding year without asking him directly.
- **Logo / photos.** None exist yet. The header uses a plain "V" mark.
- **www → root redirect** not set up — both currently serve identical content rather
  than one canonicalizing to the other. Cosmetic/SEO only, not broken.
- **Rotate the Cloudflare wrangler token** — it was briefly exposed in a chat
  transcript during setup. Short-lived token, low risk, but `wrangler logout` +
  `wrangler login` again is the clean fix whenever convenient.

## Working notes for future changes

- Custom domain bindings (`vijayas.in`, `www.vijayas.in`) were created directly via
  the Cloudflare API, not declared in `wrangler.jsonc`. They persist independently of
  deploys — a normal `git push` won't remove or need to recreate them.
- See the project memory files `vijayas_domain_dns.md` and `vijayas_address_naming.md`
  for the nameserver migration details and a naming quirk (GST address vs. Google
  Maps' Tamil name for the same street) relevant to any future Google Business
  Profile work.
