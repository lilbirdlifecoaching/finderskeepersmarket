# Finders Keepers Market — Website

Live site: **finderskeepers.market**

A family market with four sections, plus a private password-protected manager tool for adding and editing everything without touching code.

---

## Site Structure (what's live now)

| URL | What it is |
|---|---|
| `finderskeepers.market` | Homepage — brand story + interactive "Shop a Room" scene preview |
| `finderskeepers.market/shop-a-room/` | Archive of all monthly curated room scenes |
| `finderskeepers.market/furniture/` | Furniture gallery (upcycled vintage pieces) |
| `finderskeepers.market/original-art/` | Landing page for both artists — Momma Ange & Kindness Grace |
| `finderskeepers.market/kindnessgrace/` | Kindness Grace's full sculpture gallery |
| `finderskeepers.market/admin/` | Password + token protected manager tool |

There is **no Clothing page currently** — it was removed from the nav and homepage tiles until there's inventory to support it. The original-art and homepage section bar both link to "Art by Kindness Grace" rather than a generic "Original Art" label.

---

## Folder Structure

```
finderskeepersmarket/
├── index.html              ← Homepage
├── fk-styles.css           ← Shared stylesheet used by all pages
├── art-data.json           ← ALL listings + scenes (single source of truth)
├── CNAME                   ← Custom domain setting (don't touch)
├── .nojekyll                ← GitHub Pages setting (don't touch)
├── shop-a-room/
│   ├── index.html          ← Scene archive page
│   └── [scene-slug]/       ← Auto-generated per scene by the manager tool
├── furniture/
│   └── index.html
├── original-art/
│   └── index.html
├── kindnessgrace/
│   └── index.html
├── admin/
│   └── index.html          ← The manager tool (password protected)
└── images/
    ├── kg/                 ← Kindness Grace sculpture photos
    ├── wife/                ← Momma Ange art photos
    ├── furniture/            ← Furniture photos
    └── scenes/               ← Room scene photos, used by Shop a Room
```

---

## `art-data.json` — the single source of truth

Every gallery and scene on the site reads from this one file. It has these top-level arrays:

- `"wife"` — Momma Ange's art pieces
- `"daughter"` — Kindness Grace's sculptures
- `"furniture"` — furniture pieces (currently empty, ready to fill in)
- `"scenes"` — monthly "Shop a Room" scenes, including hotspot item data

You almost never need to hand-edit this file directly — the manager tool does it for you.

---

## The Manager Tool — `finderskeepers.market/admin/`

This is the only thing you need day-to-day. It's a single private page that:

- **Add New Piece** — upload a photo, fill in title/price/description/shipping, one click and it's live
- **Manage Listings** — see everything across all sections, edit any field, mark sold, delete
- **Scene Builder** — upload a room photo, click directly on the image to drop hotspot dots, fill in item details per dot, publish — it auto-creates the scene's dedicated page
- **Manage Scenes** — edit any existing scene: replace the photo, add/remove/edit hotspot items by clicking dots on the photo, set which scene is "current" (shown on the homepage), or delete a scene entirely

### First-time setup per device (one time only, ever)

1. Open `finderskeepers.market/admin/`
2. **Password screen** appears first — enter the password (ask Luke/Ange for it) — this is remembered permanently on that device
3. **GitHub token screen** appears next if no token is saved yet — paste in a GitHub Personal Access Token (ask Luke for one, or generate your own with `repo` scope under GitHub → Settings → Developer settings → Tokens classic) — also remembered permanently on that device

After that first setup, opening the tool on that device again goes straight in — no more prompts.

### Why a token is needed at all

The manager tool writes directly to the GitHub repository that powers the site (via GitHub's API) — that's what makes the "one click and it's live" magic work. The token is what authorizes those writes. It's stored only in that browser's local storage, never inside any file that gets uploaded to GitHub, so it can't be discovered or revoked by GitHub's automatic secret-scanning.

---

## Domain & Hosting

- Hosted for free on **GitHub Pages**
- Custom domain **finderskeepers.market** is connected via the `CNAME` file + DNS A records pointing to GitHub's servers
- Repo: `lilbirdlifecoaching/finderskeepersmarket`
- Changes pushed to the `main` branch go live automatically within about 60 seconds

---

## Contact Email

All inquiry buttons across the site send to **hello@finderskeepers.market** — already correctly wired everywhere as of the last brand copy update (June 2025).

---

## Brand Voice (for future copy changes)

Finders Keepers sells **emotional time travel**, not furniture. Each piece carries memory — a 1960s console becomes a bar, a childhood toy becomes a conversation piece. Copy should be specific, confident, and lead with feeling over feature lists. Bay Area, 1940s–2000s era range. Family of makers: Momma Ange (mixed media/found art) and Kindness Grace (hand-sculpted paper mache creatures).

---

## Coming Later (not yet built)

- Clothing section — once there's real inventory to show
- Instagram link in nav
- Email list signup (Mailchimp/Flodesk)
- Furniture array population as pieces are photographed
