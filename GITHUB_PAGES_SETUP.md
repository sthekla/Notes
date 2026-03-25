# GitHub Pages Setup

## Why it likely did not work yet

1. I **committed locally** in this workspace, but I cannot push to your GitHub account from here.
2. The workflow originally only deployed from the `work` branch. If you pushed `main`, it would not run.
3. GitHub Pages must be set to **Source: GitHub Actions** in repo settings.

## What was updated now

- Workflow now deploys on pushes to **both** `main` and `work`.
- Added `.nojekyll` support file to avoid static-site processing surprises.

## One-time setup in GitHub UI

1. Open your repo on GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to **GitHub Actions**.

## Commands you should run locally (on your machine)

```bash
git checkout work
# or: git checkout main

git pull
git push origin work
# if you use main instead:
# git push origin main
```

## Verify deployment

1. Go to **Actions** tab and open **Deploy static site to GitHub Pages**.
2. Wait for it to finish successfully.
3. Open:
   - `https://<your-github-username>.github.io/Notes/`

## If it still fails

- Confirm repo name is exactly `Notes` (case-sensitive in URL).
- If repo is private, verify your GitHub plan supports private Pages.
- Check the Actions logs for permission/source errors.
