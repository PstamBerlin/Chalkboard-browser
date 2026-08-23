# Hosting the Chalkboard site at chalkboard.peterstam.eu

Same trick as worlds.peterstam.eu — a free subdomain on GitHub Pages.

## 1. New GitHub repo
- Create a new public repo, e.g. **chalkboard-site**
- Upload these files (keep the names exactly):
  - `index.html`
  - `chalkboard-make-a-board.html`
  - `chalkboard-history.html`
  - `CNAME`  (contains: chalkboard.peterstam.eu)

## 2. Turn on GitHub Pages
- Repo → Settings → Pages
- Source: **Deploy from a branch** → branch **main** → folder **/ (root)** → Save
- The custom domain box should auto-fill **chalkboard.peterstam.eu** (from the CNAME file)

## 3. GoDaddy DNS
- Add a record:
  - Type: **CNAME**
  - Name / Host: **chalkboard**
  - Value / Points to: **pstamberlin.github.io**
  - TTL: default
- (This is the same as the `worlds` record, just with the name `chalkboard`.)

## 4. Wait + secure
- Give DNS a few minutes → GitHub Pages shows "DNS check successful"
- Tick **Enforce HTTPS** once the certificate is ready

## Notes
- Downloads (Mac/Windows/Firefox/Android) come from GitHub **Releases** on
  `github.com/PstamBerlin/Chalkboard-browser` — nothing big is hosted here.
- Two subdomains (worlds + chalkboard) can both point to pstamberlin.github.io;
  GitHub routes each by the CNAME file in its repo.
