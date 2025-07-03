# 🚀 Deploying MkDocs to Render (with Auto-Deploy Setup)

This guide walks you through deploying your MkDocs-based documentation site to **Render** and ensuring that it automatically redeploys on every push to GitHub.

---

## ✅ 1. Project Structure Required

Your local project should look like this:

```
folder-/
├── docs/
│   └── index.md
├── mkdocs.yml
├── requirements.txt
```

> Ensure `requirements.txt` includes:

```txt
mkdocs
mkdocs-material
mkdocs-mermaid2-plugin
```

---

## 🔄 2. Fix GitHub Auto-Deploy (If Not Working)

If auto-deploy isn't working on Render, it's likely due to a missing webhook. Here's how to fix it:

### Step-by-Step:

### 🔹 1. Disconnect GitHub from Render

1. Go to: [https://dashboard.render.com/account](https://dashboard.render.com/account)
2. Under **GitHub**, click **Disconnect**
3. Log out of Render (optional)

### 🔹 2. Remove OAuth Access on GitHub

1. Visit: [https://github.com/settings/applications](https://github.com/settings/applications)
2. Click **Authorized OAuth Apps** tab
3. Find **Render**, then **Revoke access**

### 🔹 3. Reconnect GitHub on Render

1. Log back into [https://render.com](https://render.com)

2. Click **New → Static Site**

3. Authorize GitHub again

4. Select your repo: `ALL_DOCUMENTATIONS-`

5. Fill in the config:

   | Field             | Value          |
   | ----------------- | -------------- |
   | Name              | any-name       |
   | Branch            | `main`         |
   | Build command     | `mkdocs build` |
   | Publish directory | `site`         |

6. Click **Create Static Site**

✅ Done! Render will now:

* Add a GitHub webhook automatically
* Rebuild and redeploy on every `git push`

---

## 🧪 Test It

```bash
git add .
git commit -m "Auto-deploy test"
git push
```

Check your Render dashboard — it should automatically trigger a new build.

---

## 🌐 Live Site URL

Your site will be available at something like:

```
https://your-site-name.onrender.com
```

You can find the exact link in the Render dashboard.

---

## ✅ Summary

* Render can auto-deploy on push to GitHub
* If it doesn't work, reset the GitHub connection
* Always verify that a webhook exists in GitHub settings after setup
* You don't need to run `mkdocs build` locally again — just `git push`! 💡

---
