# GoodEats promotional site

A dependency-free static landing page for GoodEats, a community for discounted food. The website introduces the community and sends visitors to Discord. It does not accept orders, payments, or requests and collects no personal information.

## What the site does

- Introduces GoodEats as a food-deals community and explains how to participate.
- Displays the supplied promotion: half off qualifying food orders, with a $30 minimum. Current eligibility and full terms are directed to Discord.
- Shows three user-supplied food photos without fabricated ratings or review quotes.
- Includes a short FAQ and links to `https://discord.gg/PMyUgUWJn`.
- Does not process orders or calculate/apply discounts; this is marketing copy only.

## Run locally

```bash
python3 server.py
```

The local preview server builds an allowlisted static bundle in `public/` and serves it on port `4173` (or the `PORT` environment variable). No order or request API is present.

## Deploy to Render

`render.yaml` defines a Render Static Site. Connect this repository as a Blueprint, or create a Static Site manually (not a Python Web Service). Its build command copies the page, hero photo, gallery photos, and licensed font into `public/`. It accepts image/font files either in `images/` and `fonts/` subfolders or flattened at the repository root. `public/` is generated during deployment and does not need to be committed. No `requirements.txt`, database, persistent disk, or staff password is needed.

After deployment, Render provides an `onrender.com` address. To use a custom domain, add it in Render and set the DNS records shown there at your domain registrar.

## Files

- `index.html` — marketing page, offer preview, community steps, photo gallery, FAQ, and styles.
- `images/group-order-editorial.jpg` — local hero image.
- `images/community-food-*.jpg` — compressed user-supplied food photos for the gallery.
- `fonts/` — local typeface and OFL license.
- `build_static.py` — allowlisted local static build.
- `server.py` — local static-only preview server.
