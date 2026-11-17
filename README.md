# 쌀독탈출 · Rice Jar Studio

Official website for Rice Jar Studio.

- Production URL: https://ricejarstudio-website.tarot1124.workers.dev/
- Cloudflare Worker name: `ricejarstudio-website`
- Static assets: `public/`
- Wrangler configuration: `wrangler.jsonc`
- Production branch: `main`

## Automatic deployment (GitHub Actions)

`.github/workflows/deploy.yml` runs on every push to `main` (and via manual **Run workflow**), then deploys using the Cloudflare Wrangler Action.

**Required GitHub Actions repository secrets:**

1. `CLOUDFLARE_API_TOKEN`: Cloudflare API token with **Edit Cloudflare Workers** permission for the intended account.
2. `CLOUDFLARE_ACCOUNT_ID`: Account ID for the Cloudflare account that hosts `ricejarstudio-website`.

Add them at **GitHub repository → Settings → Secrets and variables → Actions → New repository secret**.

Do not commit tokens, passwords or account credentials into this repository. When credentials are absent, the job intentionally fails before deployment with an actionable error.

Check deployments in **Actions → Deploy website to Cloudflare Workers** and **Cloudflare → Workers & Pages → ricejarstudio-website → Deployments**.

If a separate Cloudflare Git integration is also configured for the same Worker, disable one deployment source to avoid competing deployments.

## Website content

`public/index.html` is the live homepage. The root-level `index.html` and `styles.css` files are older drafts and are **not** deployed via Wrangler.

Policy pages: `public/privacy.html` and `public/terms.html`. Verify the privacy officer details, storage periods, and actual Cloudflare data handling before treating the legal text as final.
