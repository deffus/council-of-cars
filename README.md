# Council of Cars — Static Site

A black / red / white car enthusiast site with a homepage gallery and About Us page.

---

## File Structure

```
council-of-cars/
├── index.html       ← Homepage + image gallery
├── about.html       ← About Us page
├── style.css        ← All styles (shared)
├── images/          ← ★ Drop your car photos in here
│   ├── car01.jpg
│   ├── car02.jpg
│   └── ...          (any name works — update the src= in index.html)
└── README.md
```

---

## Adding Your Car Photos

1. Create an `images/` folder inside the project folder (if it doesn't exist).
2. Copy your `.jpg` or `.png` files into `images/`.
3. Open `index.html` in a text editor.
4. Find the gallery slots (look for `<!-- SLOT 1 -->`, `<!-- SLOT 2 -->`, etc.).
5. Update the `src=` and `alt=` of each `<img>` tag to match your filenames:
   ```html
   <img src="images/my_car.jpg" alt="My red Civic" … />
   ```
6. Update the `<div class="caption">` text to whatever you'd like shown on hover.
7. To add **more slots**, copy any complete `<div class="gallery-item"> … </div>` block and paste it after the last one, then update the `src=` and caption.

---

## Hosting on GitHub Pages (Free)

### Step 1 — Create a GitHub repository

1. Go to [github.com](https://github.com) and sign in (or create a free account).
2. Click the **+** icon → **New repository**.
3. Name it exactly: `council-of-cars` *(or anything you like — the name won't matter once you point a custom domain at it)*.
4. Set it to **Public**.
5. Click **Create repository**.

### Step 2 — Upload your files

**Option A — GitHub web interface (no Git needed)**

1. Inside your new repo, click **Add file → Upload files**.
2. Drag the entire `council-of-cars/` folder contents (not the folder itself — the files inside it: `index.html`, `about.html`, `style.css`, and your `images/` folder) into the upload area.
3. Click **Commit changes**.

**Option B — Git command line**

```bash
cd council-of-cars
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/council-of-cars.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages

1. In your repo, go to **Settings → Pages** (left sidebar).
2. Under **Source**, select **Deploy from a branch**.
3. Choose branch: **main**, folder: **/ (root)**.
4. Click **Save**.

GitHub will show you a URL like:
```
https://YOUR_USERNAME.github.io/council-of-cars/
```
Your site is live! (Can take 1–2 minutes to appear the first time.)

---

## Pointing a Custom Domain at GitHub Pages

### Step 1 — Add your domain in GitHub

1. In **Settings → Pages**, find the **Custom domain** field.
2. Type your domain, e.g. `councilofcars.com` (no `www`), and click **Save**.
3. GitHub will create a `CNAME` file in your repo automatically.

### Step 2 — Update your DNS records at your domain registrar

Log in to wherever you bought your domain (GoDaddy, Namecheap, Cloudflare, etc.) and add these DNS records:

#### For an apex / root domain (e.g. `councilofcars.com`)

Add **4 × A records** pointing to GitHub's IPs:

| Type | Name | Value          |
|------|------|----------------|
| A    | @    | 185.199.108.153 |
| A    | @    | 185.199.109.153 |
| A    | @    | 185.199.110.153 |
| A    | @    | 185.199.111.153 |

#### For a `www` subdomain (e.g. `www.councilofcars.com`)

Add a **CNAME record**:

| Type  | Name | Value                              |
|-------|------|------------------------------------|
| CNAME | www  | YOUR_USERNAME.github.io            |

> **Tip:** Most registrars let you set up *both* — the apex A records and a www CNAME — so visitors can reach the site either way. In GitHub Pages settings you can also tick **Enforce HTTPS** once the domain is verified.

### Step 3 — Wait for DNS propagation

DNS changes can take anywhere from a few minutes to 48 hours to spread worldwide.
Check progress at [dnschecker.org](https://dnschecker.org).

Once propagated, GitHub Pages will automatically provision a free SSL certificate for your domain.

---

## Making Changes Later

- Edit `index.html` or `about.html` in any text editor (VS Code, Notepad++, etc.).
- Re-upload the changed files to GitHub (drag-and-drop via the web UI, or `git push`).
- GitHub Pages re-deploys automatically within about 60 seconds.

---

## Quick Customisation Reference

| What to change | Where |
|----------------|-------|
| Site name / logo | `<a class="logo">` in both HTML files |
| Hero tagline | `.hero-sub` in `index.html` |
| Gallery captions | `<div class="caption">` in each slot |
| About Us text | The `<p>` blocks inside `.about-content` in `about.html` |
| Colours | CSS variables at the top of `style.css` (`:root {}`) |
| Add a new page | Copy `about.html`, rename it, add a link in `<nav>` of both files |

---

*Council of Cars — built for those who bleed octane.*
