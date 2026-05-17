# Finders Keepers Market — Website

Two galleries in one family:
- **finderskeepersmarket.com** → Main market (wife's art)
- **finderskeepersmarket.com/kindnessgrace/** → Art by Kindness Grace (daughter's gallery)
- **finderskeepersmarket.com/admin/** → Upload tool (for adding new pieces)

---

## Folder Structure

```
finderskeepersmarket/
├── index.html              ← Main market homepage
├── art-data.json           ← ALL artwork listings (edit this to add/update pieces)
├── CNAME                   ← Custom domain setting (don't touch)
├── .nojekyll               ← GitHub Pages setting (don't touch)
├── kindnessgrace/
│   └── index.html          ← Kindness Grace gallery page
├── admin/
│   └── index.html          ← Upload form tool
└── images/
    ├── wife/               ← Photos for main market pieces
    └── kg/                 ← Photos for Kindness Grace pieces
```

---

## How to Set Up on GitHub Pages

1. Create a free account at **github.com** if you don't have one
2. Click **New Repository** — name it `finderskeepersmarket` (or anything you like)
3. Upload all these files by dragging them into the GitHub interface
4. Go to **Settings → Pages**
5. Under "Source", select **Deploy from a branch → main → / (root)**
6. Click Save — your site will be live at `https://yourusername.github.io/finderskeepersmarket/`

---

## How to Connect Your Squarespace Domain (finderskeepersmarket.com)

1. In your **Squarespace Domains** panel, find DNS settings for finderskeepersmarket.com
2. Delete any existing A records pointing to Squarespace
3. Add these **4 new A records** (all pointing to GitHub):
   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```
4. Add a **CNAME record**:
   - Name: `www`
   - Value: `yourusername.github.io`
5. In GitHub → Settings → Pages → Custom Domain, type: `finderskeepersmarket.com`
6. Check "Enforce HTTPS" once it appears
7. DNS changes take 24-48 hours to go live

---

## How to Add New Artwork (Easy Method)

1. Go to **finderskeepersmarket.com/admin/** (or your GitHub Pages URL + /admin/)
2. Choose whose page the art goes on
3. Fill out the form — title, price, description, shipping, photo
4. Click "Generate My Listing"
5. Copy the code that appears
6. Open `art-data.json` in GitHub (click the file → pencil icon to edit)
7. Find `"wife": [` or `"daughter": [` depending on which page
8. Paste your new listing inside the brackets — add a comma after the previous last entry
9. Upload the renamed photo to `images/wife/` or `images/kg/`
10. Commit changes — site updates automatically!

---

## Updating a Piece (marking as sold, changing price, etc.)

1. Open `art-data.json` in GitHub
2. Find the piece by its title
3. Change `"available": true` to `"available": false` to mark as sold
4. Change the `"price"` number to update pricing
5. Commit — done!

---

## Contact Email

The inquiry buttons email **contact@finderskeepersmarket.com** — update this in all HTML files if your email is different.
Search for `contact@finderskeepersmarket.com` in each .html file and replace with your real email.
