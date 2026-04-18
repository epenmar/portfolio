# Elisa Penmar — Portfolio Website

A static HTML/CSS recreation of the original Wix portfolio (formerly elisapenmar.com). Zero dependencies, zero build step — just HTML, CSS, and images.

## Structure

```
Website/
├── index.html                           Home / About
├── philosophy.html
├── cv.html
├── projects.html                        Project grid / index
├── flexible-scheduling-system.html
├── advisory-curriculum-development.html
├── efficiency-and-productivity.html
├── curricula.html
├── training-and-development.html
├── escojo-ensenar.html
├── letters-of-rec.html
├── css/
│   └── style.css                        Shared stylesheet
└── images/                              73 images (headshot, project screenshots, gallery, letters)
```

## View locally

Just open `index.html` in a browser. For a slightly nicer local preview (so relative paths behave like a real server):

```bash
cd Website
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy to GitHub Pages (free, no custom domain)

1. **Create a new GitHub repo**, e.g. `elisa-portfolio` (public).

2. **Push this folder** to the repo:

   ```bash
   cd /Users/elisapenmar/Documents/Website
   git init
   git add .
   git commit -m "Initial portfolio site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/elisa-portfolio.git
   git push -u origin main
   ```

3. **Enable GitHub Pages**:
   - Go to your repo on GitHub → **Settings** → **Pages**
   - Under **Source**, pick **Deploy from a branch**
   - Branch: `main`, folder: `/ (root)` → **Save**

4. After a minute or two, your site will be live at:
   `https://<your-username>.github.io/elisa-portfolio/`

### Want the URL `<your-username>.github.io` (no repo path)?

Name the repo exactly `<your-username>.github.io` — that makes it a user site at the root of your GitHub subdomain.

## Editing content

All pages are plain HTML. To change text, open the relevant `.html` file and edit the words directly. The shared style lives in `css/style.css` — edit the `:root` variables at the top to tweak colors in one place:

```css
--accent: #a85738;   /* change the warm accent color */
--bg:     #fdfbf7;   /* page background */
--text:   #1c2434;   /* main text color */
```

The nav bar is repeated at the top of each HTML file. If you add or rename a page, update the nav block in every file.

## Contact info

Phone, email, and LinkedIn are in the footer of every page. Update them in all `.html` files if they change, or search-and-replace:

```bash
# example: change phone number everywhere
sed -i '' 's/(818) 648.8023/(NEW) NUM.BER/g' *.html
```

## Credit

Originally built on Wix. Rebuilt as plain HTML/CSS in April 2026.
