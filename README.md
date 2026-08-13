# Fantasy Football Site (Team Zamora)

Modern static web portal for the Team Zamora family fantasy football league, designed for GitHub Pages deployment.

## Repository Structure

```text
.
├── .github/
│   └── workflows/
│       └── deploy.yml      # GitHub Actions workflow for Pages deploys
├── docs/
│   ├── CNAME               # Custom domain: teamzamora.com
│   └── index.html          # Single-page static portal (HTML/CSS/JS)
└── README.md
```

## Local Preview

Because this project is a static site, you can preview it locally in either of these ways:

### Option 1: Open directly in browser
1. Open `docs/index.html` in your browser from your local clone.

### Option 2: Serve over a local HTTP server (recommended)
From repository root:

```bash
python3 -m http.server 8000 --directory docs
```

Then visit `http://localhost:8000`.

## Deployment (GitHub Pages)

Deployment is automated by `.github/workflows/deploy.yml`.

- Trigger: every push to `main` (plus optional manual trigger via `workflow_dispatch`)
- Source artifact: `docs/` directory
- Deploy action: `actions/deploy-pages`
- Domain: `teamzamora.com` via `docs/CNAME`

### One-time repository settings check
In GitHub repository settings:
1. Go to **Settings → Pages**.
2. Ensure **Source** is set to **GitHub Actions**.
3. Confirm DNS for `teamzamora.com` points to GitHub Pages.

After that, every push to `main` will publish the latest static portal automatically.
