# Push hub to GitHub

One-time setup after creating empty repo `crawloop/siemens-sieportal-automation` on GitHub.

## 1. Copy files into the repo

From this monorepo, the hub lives in:

```
hub/siemens-sieportal-automation/
├── README.md
├── docs/
│   └── index.md
└── PUSH.md
```

## 2. Push (PowerShell)

```powershell
cd C:\Users\Andrej\Desktop\Apify\hub\siemens-sieportal-automation

git init
git add README.md docs/ PUSH.md
git commit -m "Add Siemens Automation Suite hub"

git branch -M main
git remote add origin https://github.com/crawloop/siemens-sieportal-automation.git
git push -u origin main
```

If the GitHub repo was created **with** a README, pull first:

```powershell
git pull origin main --rebase
git push -u origin main
```

## 3. Configure GitHub repo About

| Field | Value |
| :--- | :--- |
| **Description** | Official hub for Crawloop Siemens Automation Suite — Apify actors for SiePortal MPN discovery, lifecycle checks, SIOS documents, and TED datasheet extraction. |
| **Website** | `https://crawloop.github.io/siemens-sieportal-automation/` (after step 4) |
| **Topics** | `siemens`, `siemens-sieportal`, `industrial-automation`, `apify`, `web-scraping`, `procurement`, `bom`, `mpn` |

## 4. Enable GitHub Pages

1. Repo → **Settings** → **Pages**
2. **Build and deployment** → Source: **Deploy from a branch**
3. Branch: **main**, folder: **/docs**
4. Save — site live in ~1 min at `https://crawloop.github.io/siemens-sieportal-automation/`

## 5. Optional — link from Apify READMEs

Add under the suite header in each Siemens actor README on Apify:

```markdown
Suite hub: [github.com/crawloop/siemens-sieportal-automation](https://github.com/crawloop/siemens-sieportal-automation)
```

Then redeploy actors: `python tmp/deploy_all_siemens.py`
