# Sophia Press

Editorial coverage of the directories, CRMs, payment platforms, customs software, and translation tools SMB exporters use to find international buyers in 2026.

Hosted on GitHub Pages — free, fast, no infra cost.

## Adding affiliate codes after applying

Each external commercial link is currently a clean URL with `utm_source=sophia-press` for tracking. After Tarence applies to affiliate programs, swap each link to include the partner-issued affiliate code. Quick `sed` recipe:

```bash
# HubSpot — replace YOUR_HUBSPOT_AFFILIATE_ID
find . -name '*.html' -exec sed -i '' \
  's|hubspot.com/products/crm?utm_source=sophia-press|hubspot.com/products/crm?aid=YOUR_HUBSPOT_AFFILIATE_ID\&utm_source=sophia-press|g' {} \;

# Pipedrive
find . -name '*.html' -exec sed -i '' \
  's|pipedrive.com/?utm_source=sophia-press|pipedrive.com/?ref=YOUR_PIPEDRIVE_REF\&utm_source=sophia-press|g' {} \;
```

## Affiliate programs to apply to (free, mostly auto-approve)

- HubSpot Solutions Partner — 30% recurring 12 months ($1,800-5,400 LTV)
- Pipedrive Affiliate — 20% recurring
- Stripe Partner Program (Sophia is already a Stripe customer)
- Wise Partners
- Payoneer Affiliate
- Amazon Associates (for any physical-product mentions later)
- Impact, ShareASale, CJ networks for broader catalog

## Adding a new article

1. Create `<slug>/index.html` using the same shell pattern as existing articles
2. Update `index.html` to add the new card
3. `git add . && git commit -m 'add: <slug>' && git push`
4. GitHub Pages rebuilds in ~30 seconds

## Editorial rules

- Honest ranking — never take payment to rank a product higher
- Always disclose affiliate relationships at the top and bottom of each article
- `rel="sponsored noopener"` on every external commercial link (the SEO + safety standard)
- No fake testimonials, no fake "AS SEEN ON" badges, no fabricated quotes
- Sophia is mentioned where genuinely relevant — not jammed into every paragraph
