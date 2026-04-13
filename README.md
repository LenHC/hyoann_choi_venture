# GT Deep Tech Founder HOW-TOs
**Your personal website + article series for the GT researcher community**

---

## File structure

```
your-site/
├── index.html              ← Homepage (bio + article cards)
├── assets/
│   └── flyer.css           ← Shared styles for all articles
├── articles/
│   ├── 01-healthcare-stakeholders.html
│   ├── 02-dilutive-nondilutive-funding.html
│   ├── 03-patent-strategy.html
│   ├── 04-regulatory-pathways.html
│   └── 05-communicating-investors.html
└── README.md               ← This file
```

---

## How to deploy on GitHub Pages (free hosting)

### Step 1 — Create a GitHub account
Go to [github.com](https://github.com) and sign up if you don't have an account.

### Step 2 — Create a new repository
1. Click the **+** icon (top right) → **New repository**
2. Name it exactly: `your-username.github.io`  
   *(Replace `your-username` with your actual GitHub username)*
3. Set visibility to **Public**
4. Click **Create repository**

### Step 3 — Upload your files
**Option A — Drag and drop (easiest):**
1. Open your repository on GitHub
2. Click **uploading an existing file**
3. Drag the entire `your-site/` folder contents into the browser window
4. Click **Commit changes**

**Option B — GitHub Desktop (recommended for ongoing edits):**
1. Download [GitHub Desktop](https://desktop.github.com)
2. Clone your repository to your computer
3. Copy all files into the cloned folder
4. In GitHub Desktop: write a commit message → click **Commit to main** → **Push origin**

### Step 4 — Enable GitHub Pages
1. Go to your repository → **Settings** → **Pages** (left sidebar)
2. Under "Source", select **Deploy from a branch**
3. Branch: **main**, Folder: **/ (root)**
4. Click **Save**

### Step 5 — Your site is live!
After ~2 minutes, your site will be live at:
```
https://your-username.github.io
```

---

## How to edit content

### Edit your bio (index.html)
Open `index.html` and look for the `✏️ EDIT` comments:
- **Line ~100**: Your name, tagline, and bio paragraph
- **Line ~115**: Your focus area pills (add/remove as needed)
- **Line ~200**: Footer name and LinkedIn URL

### Edit an article
Each article file has `✏️` comments marking every editable section:
- **Header**: eyebrow number, title, subtitle
- **Cards**: role names, descriptions, examples
- **Key insight**: the one-sentence takeaway
- **Footer**: link to next article

### Add a new article
1. Copy any existing article file and rename it (e.g. `06-reimbursement-strategy.html`)
2. Edit all `✏️` sections with your new content
3. Open `index.html` and find the `ARTICLES` array in the `<script>` block
4. Copy one article object and fill in: `num`, `title`, `desc`, `file`, `tags`
5. Available tag types: `industry`, `funding`, `legal`, `regulatory`, `strategy`, `markets`

### Change the accent color of an article
At the top of each article file, there's a `<style>` block with four CSS variables:
```css
:root {
  --accent:       #185FA5;   /* main color */
  --accent-light: #E6F1FB;   /* background tint */
  --accent-dark:  #0C447C;   /* darker shade */
  --accent-deep:  #042C53;   /* darkest, for text */
}
```
Swap these to any of the palette colors listed in `assets/flyer.css`.

---

## How to add images or figures to articles

1. Create an `assets/images/` folder
2. Drop your image file in (e.g. `my-figure.png`)
3. In any article, add this HTML where you want the image:
```html
<img src="../assets/images/my-figure.png" alt="Description of figure"
     style="width: 100%; border-radius: 8px; margin: 1rem 0;">
```

---

## Sharing as print flyers

Open any article in Chrome → **File → Print → Save as PDF**  
Set margins to "None" or "Minimum" for a clean one-pager.

---

## Optional: custom domain (e.g. yourname.com)

1. Buy a domain from [Namecheap](https://namecheap.com) or [Google Domains](https://domains.google)
2. In your repo → Settings → Pages → Custom domain → enter your domain
3. Follow the DNS setup instructions GitHub shows you
4. Takes ~24 hours to propagate

---

*Built with plain HTML/CSS — no frameworks, no build tools, no dependencies.*  
*Edit any file in a text editor (VS Code recommended) and push to GitHub to update your live site.*
