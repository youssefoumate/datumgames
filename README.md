# datumgames.github.io

The public site for **Datum Games** — a studio page, and the canonical home of
Dwida's privacy policy and data-deletion instructions.

Live at <https://youssefoumate.github.io/datumgames/>.

## Why this exists as its own repo

Google Play requires three public URLs that the game repo cannot provide:

- a **developer website**, asked for during account verification
- a **privacy policy**, required for every app
- a **data deletion** page, required once an app collects anything

The game's repo (`oberth`, the working title — the game is now called Dwida) is private, and GitHub Pages will not serve a private repo on
a free plan. Publishing the game's own `docs/` folder would also have put the
build and publishing runbooks — including account strategy — on the open web.
So the public pages live here and the source stays private.

These pages replace two gists that previously held the same text.

## Structure

```
index.html        studio page + links
privacy.html      Dwida privacy policy
delete-data.html  how to request deletion
style.css         shared styles, the game's palette
.nojekyll         serve the files as-is, no Jekyll build

googlea119ff78ea7500b7.html   Google site-ownership token — DO NOT DELETE
```

That last file looks like junk and is not. It is how Google proves this site
belongs to us, and Google **re-checks it periodically** — remove it and the site
silently becomes unverified, which takes the Play Console developer-website
verification down with it. It has no content worth reading; leave it alone.

No build step, no dependencies, no JavaScript. Edit the HTML and push.

## Keeping it truthful

`privacy.html` and `delete-data.html` are the *published* versions of
`docs/PRIVACY.md` and `docs/DELETE_DATA.md` in the `oberth` repo. If either
changes there, change it here too — a privacy policy that disagrees with the app
is worse than not having one, and Play compares them during review.

The two facts most likely to go stale, because both are marked "not currently"
and both are expected to change:

- **Sentry is disabled.** The policy says so. Enabling crash reporting means
  updating this page *before* the build ships.
- **Purchases go through RevenueCat.** Both products (the full unlock and the
  skin pack) are verified by it, and the policy names it as a service provider.
  A new product, or a new SDK that touches purchase data, means re-reading the
  Purchases and Service providers sections.

## Custom domain

Pages supports one. Add a `CNAME` file with the domain and point a DNS `CNAME`
record at `youssefoumate.github.io`. Nothing else changes, and the old URLs keep
working.
