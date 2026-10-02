# finai-app-redirect

Redirects every URL on `app.financeai.cloud` to https://financeai.cloud/paused/ while the FinanceAI app is paused.

Served by GitHub Pages:

- `CNAME` claims the `app.financeai.cloud` custom domain.
- `index.html` redirects the root.
- `404.html` (a copy of `index.html`) redirects every other path, so old deep links like `/login` land on the paused page too.

DNS (GoDaddy): `app` is a CNAME to `rclewis.github.io`.

The redirect is client-side (meta refresh + `location.replace`), since GitHub Pages can't send HTTP 301s.

To retire it, remove the `app` DNS record **before** deleting this repo or its Pages custom domain. Otherwise the subdomain is left pointing at GitHub with nothing claiming it.
