# recount.ackerworks.com

Marketing site for [Recount](https://github.com/VDC-Austin-KA/Recount) — local voice
dictation for Windows.

Plain HTML and one stylesheet. No build step, no framework, no dependencies.

```
docs/
  index.html     landing page
  privacy.html   privacy policy
  terms.html     licence terms
  style.css      shared tokens - both pages link it so they cannot drift apart
```

## Deploying

Two independent paths, so one being blocked does not stop the other:

- **GitHub Pages** serves `docs/` straight from the branch. No Actions run, no secrets,
  no billing — live at https://vdc-austin-ka.github.io/recount-site/
- **Cloudflare** serves the same directory at recount.ackerworks.com once credentials
  exist.

Pushes to `main` deploy automatically. Add two repository secrets first, both copyable
from the `ackworks` repo settings:

- `CLOUDFLARE_API_TOKEN`
- `CLOUDFLARE_ACCOUNT_ID`

Or deploy by hand: `npx wrangler login && npx wrangler deploy`.

## Before this goes live

`index.html` carries an **honesty audit** in an HTML comment listing which claims are true
today and which are deliberately written in future tense. Read it before editing copy.
Promoting a future-tense claim early is the one change that would make the product's
honesty positioning false.

`privacy.html` and `terms.html` are **drafts and have not been reviewed by a lawyer.**
