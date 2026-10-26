# Liana Khazaliya — Academic Website

A finished, lightweight academic homepage for **https://lkhazaliya.com/**, based on the October 2026 CV and the supplied portrait.

## What's included

- `index.html` — all site copy and content; edit with any text editor.
- `assets/style.css` — colors, typography, layout and mobile styling.
- `assets/site.js` — tiny mobile navigation script; no framework or installation required.
- `assets/liana-portrait.webp` — optimized version of your supplied photograph.
- `assets/favicon.svg` — site icon.
- `files/Liana_Khazaliya_CV.pdf` — original CV PDF.
- `CNAME` — GitHub Pages custom-domain setting (`lkhazaliya.com`).
- `.nojekyll` — disables unnecessary GitHub Pages processing.
- `robots.txt` and `sitemap.xml` — simple search engine discovery metadata.

The website has **no trackers, cookies, paid dependencies, build step, or recurring hosting fee** on GitHub Pages. Your domain registration is separate, and must be renewed.

## Test locally

Double-click `index.html` to open the page. Or run a local server from this folder:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000 in your browser. (On Windows, the command may be `py -m http.server 8000`.)

## Publish to GitHub Pages (recommended)

**Prerequisites:** You control the domain `lkhazaliya.com` and its DNS settings, and have a GitHub account. A public repository is enough for free GitHub Pages.

1. Go to https://github.com/new. Create a **public** repository, for example `lkhazaliya-site`. Create it empty if possible.
2. Open the new repository and choose **Add file → Upload files**. From *inside the unzipped website folder*, select/upload **all files and folders**, including `index.html`, `assets`, `files`, and `CNAME`. GitHub's browser upload may not include hidden `.nojekyll`; that file is optional for this simple site. Commit files to the `main` branch. **Important:** `index.html` must be in the repository root, not inside an extra outer folder.
3. In your repository, open **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**. Select branch `main`, folder `/(root)`, then **Save**.
4. Still in **Settings → Pages**, under **Custom domain**, enter **`lkhazaliya.com`**, then click **Save**. Do this **before** pointing DNS records to GitHub Pages. Your supplied `CNAME` file also contains the correct domain.
5. In your domain registrar's DNS dashboard (where the domain's nameservers are configured), add these **four** A records for the root domain. Names may appear as `@` or left blank, depending on the provider:

   | Type | Name/Host | Value |
   | --- | --- | --- |
   | A | @ | 185.199.108.153 |
   | A | @ | 185.199.109.153 |
   | A | @ | 185.199.110.153 |
   | A | @ | 185.199.111.153 |

6. For **`www.lkhazaliya.com`**, add a **CNAME** record:

   | Type | Name/Host | Value |
   | --- | --- | --- |
   | CNAME | www | **YOUR-GITHUB-USERNAME**.github.io |

   Replace `YOUR-GITHUB-USERNAME` with your actual GitHub account name. **Do not** append `/lkhazaliya-site`, `https://`, or the repository name. GitHub will redirect `www` to the root domain when both are configured. Do not create a CNAME for the bare root `@`.

7. Remove **conflicting** old A/AAAA/ALIAS/ANAME root records and conflicting `www` records **only after checking what they are for**. Do **not** delete MX, TXT, SPF, DKIM, DMARC or other email records—those may be required to keep your email working. If your DNS is managed by another provider (e.g., Cloudflare), edit DNS at that provider, not necessarily the registrar.
8. Wait for DNS to propagate (it can take up to **24 hours**). Go back to **Settings → Pages**; after GitHub provisions its certificate, enable **Enforce HTTPS**. Visit both https://lkhazaliya.com and https://www.lkhazaliya.com to check the redirect and SSL.

You can optionally verify ownership of the domain in GitHub account settings first, to reduce the risk of domain takeover. See official GitHub help below.

### Troubleshooting

- **Repository site is empty/404?** `index.html` must be at the root and Pages source must be `main / (root)`. Inspect the repository's Actions tab or Pages settings for deployment errors.
- **Custom domain not opening?** Confirm that GitHub has your custom domain set to `lkhazaliya.com`, then check A records and `www` CNAME. Your GitHub username has to be exact.
- **HTTPS checkbox disabled?** Allow time for certificate issuance and correct or remove conflicting records. Confirm domain propagation.
- **Registrar says `@` not valid?** Many providers use an empty host/name field instead.
- **You're using Cloudflare and seeing redirect loops?** Make sure proxy and SSL settings do not conflict with GitHub Pages; DNS-only mode during setup can simplify troubleshooting.
- **Need a preview URL?** After GitHub Pages is enabled, the site normally has a GitHub Pages URL like `https://USERNAME.github.io/lkhazaliya-site/`; when custom domain is active, it redirects to `lkhazaliya.com`.

## Update the site later

Update `index.html` directly from the GitHub web editor (`index.html` → pencil icon → Commit changes) or upload replacement files. GitHub automatically republishes committed changes. To replace your CV, upload a PDF with exactly the same name, `files/Liana_Khazaliya_CV.pdf`, so the buttons still work. To update the portrait, create a new WebP file and replace `assets/liana-portrait.webp` (or update the path in HTML).

## Notes about privacy and content

The page intentionally publishes your Aalto email address, but **not** the phone number or postal address from your CV. The linked original CV does contain more personal contact information—review it before publication. The supplied photo filename identifies **Nadja Meister** as the photographer; credit is retained under the portrait. Publications are linked to verified preprint or DBLP record URLs, and Scholar/ORCID/DBLP profiles have been linked.

## Official instructions

- GitHub Pages: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- Custom domain / DNS / redirect: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site
- Domain verification: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages

---

**This zip is prepared for deployment, not deployed.** Publishing and domain DNS changes require action in accounts you own.
