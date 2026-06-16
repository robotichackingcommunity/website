# website

Official static website for the Robotic Hacking Community — DEF CON 34.

A plain HTML/CSS static site with no build tools or backend dependencies.

## Project Structure

```
index.html      Home
about.html      About
program.html    Program
cfp.html        Call for Papers
images/         Images and favicon assets
CNAME           Custom domain config (GitHub Pages)
```

## Running Locally

### Option 1: Local server (recommended)

From the project root, run:

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000> in your browser.

### Option 2: VS Code Live Server

Install the Live Server extension, then right-click `index.html` →
"Open with Live Server" for live reload on save.

### Option 3: Open directly

Open `index.html` directly in your browser. Note that when opened via
`file://`, some browsers are stricter about relative paths and font
loading, so a local server is preferred.

## Deployment

Deployed via GitHub Pages, with the domain set by `CNAME`. Pushing to the
default branch updates the live site.
