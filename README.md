# MOC Email Signature (MOC-TPL-SIG)

Internal tool that builds the standard MOC email signature. Staff fill in their details, copy
the finished signature, and paste it into Outlook.

- `index.html`: the whole tool (one static page, no build step, no dependencies)
- `icon.svg`, `apple-touch-icon.png`: browser and home-screen icons

The page follows MOC-BSM-001: black and white only, the MOC font stack (Proxima Nova, Helvetica
Neue, Arial), caps labels at 0.10em, `//` separators. The signature itself uses Arial, since
it has to render the same in every email app, and pulls the box logo from the brand site
(`moc-brand-site.vercel.app/assets/logo/moc-box-primary.png`).

## Deploy

One process for every MOC site: push to `main` on GitHub (`SiPEONER/moc-email-signature`) and
Vercel deploys it automatically to moc-email-signature.vercel.app. No CLI or upload deploys.

```bash
git add .
git commit -m "Describe the change"
git push origin main
```

Commit as `SiPEONER <SiPEONER@users.noreply.github.com>` so Vercel matches the author to the team.
