# Deploying to Netlify

Quick steps to publish this site to Netlify from this repository.

1. Install the Netlify CLI (optional but convenient):

```bash
npm install -g netlify-cli
```

2. Login to Netlify:

```bash
netlify login
```

3. From the project root, deploy a production site:

```bash
# one-time initialization (creates or links a Netlify site)
netlify init

# or deploy directly (fast):
netlify deploy --dir=. --prod
```

4. Add custom domain `yadidyamusicals.com` in the Netlify dashboard:
- Open your site on Netlify → Domain settings → Add custom domain
- Enter `yadidyamusicals.com` and follow the verification steps

5. Update DNS at your domain registrar:
- For `www` subdomain: add a CNAME pointing `www` → `your-site.netlify.app` (Netlify gives the exact target)
- For root domain (`yadidyamusicals.com`): use an ALIAS/ANAME if your registrar supports it, or point the A records Netlify provides (see dashboard)

Notes:
- Netlify provides automated HTTPS (Let’s Encrypt) once DNS is configured and propagated.
- You can drag-and-drop the folder on the Netlify Sites dashboard instead of using CLI if you prefer a web flow.
