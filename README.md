# website

Official static website for the Robotic Hacking Community and the RHC Physical AI Vulnerability Database.

A plain HTML/CSS static site with no build tools or backend dependencies.

## Project Structure

```
index.html              Home
physical-ai-vulnerability-database.html
                        RHC Physical AI Vulnerability Database explorer
research-hub.html       Research Hub (coming soon)
open-source-badge.html  RHC open-source badge
def-con-34.html         DEF CON 34 recap, links to the event pages below
news-and-updates/       News list (news-and-updates.html) and article pages;
                        article images go in images/news/
news-and-updates.html, vicone-radeis-extension-nvidia-isaac-sim.html,
physical-ai-safety-stress-test-def-con-34.html
                        Redirects from the old root URLs into news-and-updates/
about.html              About
program.html, cfp.html, ctf.html, rrc.html, badge.html
                        DEF CON 34 event pages (kept, linked from def-con-34.html)
images/                 Images and favicon assets
CNAME                   Custom domain config (GitHub Pages)
```

Records are not stored here: `physical-ai-vulnerability-database.html` is a search/filter
explorer (fields and filters mirror pa-vd.robotichackingcommunity.com) that fetches `index.json` from the
[PA_VD repo](https://github.com/robotichackingcommunity/PA_VD) at page
load, and each record's `CVE-json/*.pavd.json` when its detail is opened
through the GitHub contents API, so a push to PA_VD shows up within about a
minute. If a visitor runs out of the API's 60 unauthenticated requests per
hour, it falls back to pa-vd.robotichackingcommunity.com and then raw.githubusercontent.com, which
CDN-cache for up to 10 and 5 minutes. The homepage Vuln DB card reads its
record count the same way.

Logos are WebP (`images/logo-nav.webp`, `images/logo-hero.webp`, generated
from `images/logo.png`). Don't inline images as base64.

## Running Locally

### Option 1: Local server (recommended)

From the project root, run:

```bash
npm start
```

Then open <http://localhost:8000> in your browser. There is nothing to
install: the script just runs `python3 -m http.server 8000`, which you can
also run directly.

### Option 2: VS Code Live Server

Install the Live Server extension, then right-click `index.html` →
"Open with Live Server" for live reload on save.

## Deployment

Deployed via GitHub Pages, with the domain set by `CNAME`. Pushing to the
default branch updates the live site.
