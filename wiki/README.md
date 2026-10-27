# EP11 Developer Blog & GitHub Wiki

This directory stores the source markdown files for the repository's **GitHub Wiki (Blog)**.

---

## 🛠️ How GitHub Wiki Publishing Works

GitHub Wikis are Git repositories behind the scenes (`https://github.com/<owner>/<repo>.wiki.git`).

### Option 1: Manual Push to GitHub Wiki (One-Time / As Needed)

```bash
# 1. Enable Wikis in your GitHub repository Settings > Features > Wikis
# 2. Create the first dummy page in the GitHub Web UI to initialize the wiki git repo
# 3. Clone the wiki repository:
git clone https://github.com/<owner>/<repo>.wiki.git /tmp/wiki

# 4. Copy all files from this directory into the wiki clone:
cp -r wiki/* /tmp/wiki/

# 5. Commit and push:
cd /tmp/wiki
git add .
git commit -m "Publish EP11 Developer Blog & Wiki pages"
git push origin master
```

### Option 2: Automatic Sync via GitHub Actions

You can automate syncing this `wiki/` directory to GitHub Wiki on every push to `main` using an action such as `SwiftDocOrg/github-wiki-publish-action` or a simple git push script in `.github/workflows/wiki-sync.yml`.
