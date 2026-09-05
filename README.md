# RecallAware public pages

Privacy policy, terms of service, support/contact page, and a small landing
page for RecallAware — meant to be hosted on GitHub Pages so you have stable
public URLs for App Store Connect / Play Console.

## First-time setup

1. **Before pushing anything, fill in two placeholders:**
   - In `support.html`, replace `REPLACE_WITH_YOUR_CONTACT_EMAIL` (appears
     twice) with the real email address you want testers and app-store
     reviewers to use.
   - In `terms-of-service.html`, replace `[YOUR STATE/COUNTRY —
     placeholder, fill in before publishing]` in the "Governing law" section
     with the actual state/country whose law should govern the terms (e.g.
     "the State of Florida, USA"). This is a real legal decision — worth
     a quick check with an actual lawyer if you're not sure, same as the
     "not legal advice" note already on both the privacy policy and terms
     pages.

2. Create a new **public** repo on GitHub (a private repo's Pages site
   requires GitHub Pro/Team — public is simplest and fine for docs like
   these). Suggested name: `recallaware-pages` (or whatever you like).

3. From this folder, run:
   ```
   git init
   git add .
   git commit -m "Public pages: privacy policy, terms of service, support, home"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```

4. On GitHub: go to the repo's **Settings → Pages**, set **Source** to
   "Deploy from a branch," branch `main`, folder `/ (root)`, and save.
   GitHub will give you a URL like:
   ```
   https://<your-username>.github.io/<repo-name>/
   ```
   (takes a minute or two to go live the first time).

5. Use these in App Store Connect / Play Console:
   - **Privacy Policy URL:** `https://<your-username>.github.io/<repo-name>/privacy-policy.html`
   - **Terms of Service URL (if asked):** `https://<your-username>.github.io/<repo-name>/terms-of-service.html`
   - **Support URL:** `https://<your-username>.github.io/<repo-name>/support.html`

6. **Once it's live, send the real base URL back** so the app's Profile
   screen Privacy Policy / Terms of Service links (currently dead —
   `onTap: () {}`) can be wired to open these pages for real via
   `url_launcher` (already a dependency in `pubspec.yaml`).

## Updating later

Edit the `.html` files and re-run `git add . && git commit -m "..." && git push`
— GitHub Pages redeploys automatically within a minute or two.
