# MOC Email Signature — deploy to moc-email-signature.vercel.app

This folder has one file: `index.html`. It's the finished, QA'd signature tool
(same version as the Claude artifact), already wrapped as a complete static
page — no build step, no dependencies, no server.

## Why I couldn't deploy this myself

I tried to run the Vercel CLI from here and also from a shell on this Mac,
and both times `npm` was blocked (403 Forbidden from the npm registry) before
it could even install `vercel`. I also don't have a token for your Vercel
account, so I can't deploy to your account via its API either way. Vercel
deploys are tied to your login, so this last step has to run from your own
terminal.

## Deploy it (2 minutes)

From a normal Terminal window on this Mac (not through any assistant tool):

```bash
cd ~/moc-email-signature-deploy   # the folder you saved these two files into
npx vercel --prod
```

First run will ask you to log in (choose the same method you used for
moc-brand-site — looks like GitHub) and to confirm the project settings:

- **Set up and deploy?** Yes
- **Which scope?** your account/team
- **Link to existing project?** No
- **Project name?** `moc-email-signature` — this is what fixes the URL to
  `moc-email-signature.vercel.app`
- **Directory?** `./` (current folder)
- Vercel will detect it as a static site automatically — no framework, no
  build command needed.

That's it — it deploys immediately and gives you the live URL. Future edits:
drop a new `index.html` in this same folder and run `npx vercel --prod` again.

## If `npx vercel` also fails for you

Use the Vercel dashboard instead, no CLI required:

1. Push this folder to a new GitHub repo (or add it to an existing one).
2. In the Vercel dashboard: **Add New… → Project → Import** that repo.
3. Framework preset: **Other** (plain static site — Vercel will just serve
   `index.html`).
4. Set the project name to `moc-email-signature` before deploying, so the
   URL matches.
