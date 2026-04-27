# LinkPulse — Static QR Visit Counter

100% static. No backend. No database. Free forever on GitHub Pages.

## How it works

| File | Purpose |
|------|---------|
| `index.html` | Dashboard — add links, view counts, generate QR codes |
| `visit.html` | Redirect page — every QR scan hits this page first, counts +1, then forwards the visitor |

**Count storage:** Uses [CountAPI.xyz](https://countapi.xyz) — a free, anonymous hit counter API. Each link gets a unique key derived from its URL. No sign-up needed.

**Link/settings storage:** Browser `localStorage` — stays on the user's device.

---

## Deploy in 3 steps

### 1. Create a GitHub repo
- Go to [github.com/new](https://github.com/new)
- Name it anything, e.g. `linkpulse`
- Set it to **Public** (required for free GitHub Pages)

### 2. Upload both files
- Upload `index.html` and `visit.html` to the root of the repo

### 3. Enable GitHub Pages
- Repo → **Settings** → **Pages**
- Source: **Deploy from a branch** → `main` → `/ (root)`
- Click **Save**

Your site will be live at:
```
https://<your-github-username>.github.io/<repo-name>/
```

---

## First-time setup in the dashboard

1. Open your GitHub Pages URL
2. Paste your GitHub Pages URL into the **"Your GitHub Pages URL"** field and click **Save**
   - This makes QR codes point to your `visit.html` on the live site
3. Add links and share the generated QR codes!

---

## Usage

- **Add a link** → paste any URL → click "Add & Generate QR"
- **Share the QR code** → download or copy the tracking URL
- **When someone scans** → they hit `visit.html` → count increments via CountAPI → they're redirected to the real URL
- **View counts** → click "Refresh Counts" anytime, or they auto-load on page open

---

## Limitations

- CountAPI is a free public service — counts are permanent and global per key
- `localStorage` means link list is device-specific (not synced across devices)
- No analytics beyond total + daily counts

---

## Files

```
your-repo/
├── index.html   ← Dashboard
└── visit.html   ← Visit counter + redirect
```
