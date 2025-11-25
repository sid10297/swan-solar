# Deploying Swan Solar to Vercel

These steps replace the current `energyswan.in` site with this Framer export.

---

## 1. Prep the repository
1. Ensure the latest code (including `vercel.json`) is committed.
2. Push to GitHub:  
   ```bash
   git add .
   git commit -m "Prepare Vercel deployment"
   git push origin master
   ```

---

## 2. Create the Vercel project
1. Sign in at https://vercel.com with GitHub.
2. Click **New Project → Import Git Repository**.
3. Select this repo and keep defaults:
   - Framework Preset: **Other**
   - Build command: *(leave empty)*
   - Output directory: `.`  
4. Click **Deploy**. Vercel will publish to `https://<project>.vercel.app`.

---

## 3. Point `energyswan.in` to Vercel
1. In the Vercel dashboard open the project → **Settings → Domains**.
2. Add `energyswan.in` (and `www.energyswan.in` if needed).
3. Update DNS at your registrar:
   - Root domain: set an **A** record to `76.76.21.21` (Vercel edge).
   - `www`: set a **CNAME** to `cname.vercel-dns.com`.
4. Wait for propagation (typically <30 min). Vercel auto-provisions HTTPS.

---

## 4. Verify
1. Visit `https://energyswan.in` on desktop & mobile.
2. Check each page (`/about`, `/ac-lighting`, service pages, articles).
3. Confirm images/fonts load and contact links work.

---

## 5. Going forward
- Every `git push` to `master` redeploys automatically.
- Use Vercel preview deployments to test branches before merging.
- Manage environment variables or headers in Vercel Settings if needed later.

