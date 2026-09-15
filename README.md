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

**No CI, no Actions, no secrets.** Pushing to `main` is the deploy: GitHub Pages serves
`docs/` straight from the branch using its legacy builder, which runs no Actions job.

Live at https://vdc-austin-ka.github.io/recount-site/

For the custom domain, run it yourself when you want it — also no CI:

```
npx wrangler login
npx wrangler deploy
```

That puts the same `docs/` directory on recount.ackerworks.com.

## Before this goes live

`index.html` carries an **honesty audit** in an HTML comment listing which claims are true
today and which are deliberately written in future tense. Read it before editing copy.
Promoting a future-tense claim early is the one change that would make the product's
honesty positioning false.

`privacy.html` and `terms.html` are **drafts and have not been reviewed by a lawyer.**
