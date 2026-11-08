---
name: ship-check
description: Pre-launch audit for a web app - leaked secrets in client code, Supabase keys and Row Level Security, Stripe webhook signature checks, and the basics Google needs to index the site (real links, real URLs, unique titles, no leftover noindex). Use before launching, before a big deploy, or when the user asks "is this safe to ship?" or "why isn't my site on Google?".
---

# Ship check

Audit the project for the items below. **Report first, change nothing yet.** For each finding give the
file and line, why it matters (one sentence), and the proposed fix. Then wait for the user's OK.

## Security
1. Secrets in client code: any secret in a `NEXT_PUBLIC_` or `VITE_` variable, or otherwise bundled into
   code the browser downloads.
2. A Supabase secret / `service_role` key used anywhere outside server code.
3. Supabase tables without Row Level Security enabled, or with policies that let anyone read or write
   private data (check migrations and `supabase/` SQL).
4. Stripe webhook handlers that don't verify the `Stripe-Signature` header with the endpoint secret on the
   raw request body, or that grant access from data the browser sends.

## Can Google index it?
5. Navigation built with buttons or `onClick` handlers instead of `<a href>` links (or the framework's Link).
6. Hash routes (`/#/page`) instead of real URLs.
7. Pages that share the same `<title>` or meta description (including template defaults like "Vite + React").
8. Any `noindex` robots meta tag or `X-Robots-Tag` header, or a `robots.txt` rule that blocks the site.

## Output
A table: `# | finding | file:line | fix`, sorted most serious first, then "Nothing found" for each item
that's clean. End by asking which fixes to apply.

Sources: Next.js and Vite env var docs, Supabase API keys and RLS docs, Stripe webhooks docs, Google Search
Central (crawlable links, JavaScript SEO basics, title links, block indexing).
