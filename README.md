# WOA Operations

**Workers of Art** — studio task management. All 7 views in a single file.

> Task Entry · Project View · Architect View · Project Dashboard · Weekly Review · Monthly Report · Sync & Settings

---

## Host on GitHub Pages (2 min)

1. **Create a new GitHub repo** (or use an existing one).
2. Upload `index.html` to the **root** of the repo.
3. Go to **Settings → Pages → Deploy from a branch** → branch `main`, folder `/ (root)`.
4. Click **Save** — your app is live at `https://<your-username>.github.io/<repo-name>/` within ~1 minute.

That's it. No build step, no server, no dependencies to install.

---

## Run locally

Double-click `index.html` — it opens in any browser and works offline (except the Geist webfont, which needs an internet connection).

---

## How it works

| File | Purpose |
|------|---------|
| `index.html` | The entire app — tokens, components, all 7 views |

**External CDN dependencies** (public, always available):
- React 18 + ReactDOM + Babel (inline JSX, dev build)
- Geist font via Google Fonts

**Persistence:** Tasks and the team roster are saved to `localStorage` — every create, update, delete, and assignee change survives a page reload. Use the **Reset demo** button to restore the sample dataset. For real cross-device sync, wire up a Firebase Realtime Database URL on the **Sync & Settings** tab.

---

## Notes

- The "in-browser Babel transformer" console message is a normal dev notice, not an error.
- To self-host the font offline, download the Geist WOFF2 files and replace the `@import` at the top of the `<style>` block with local `@font-face` rules.
- For a production build, precompile the JSX with Vite or esbuild and swap the Babel CDN tag for the compiled output.

