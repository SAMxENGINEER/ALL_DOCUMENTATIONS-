##  Complete Guide:

---

### 🧱 0. Prerequisites

✅ Make sure you have these:

* [x] `git` installed — check with:

  ```bash
  git --version
  ```

* [x] A GitHub account — [https://github.com](https://github.com)

* [x] project folder:

---

## ✅ 1. Initialize Git in Your Project

Open terminal inside your project folder:

```bash
cd path/to/project-floder
git init
```

This starts tracking the folder with Git.

---

## ✅ 2. Add and Commit Files

```bash
git add .
git commit -m "Initial commit with anyname project"
```

---

## ✅ 3. Create a Repo on GitHub

1. Go to [https://github.com/new](https://github.com/new)
2. Name it: `ALL_DOCUMENTATIONS-`
3. Leave everything default (don’t add README)
4. Click **Create repository**

---

## ✅ 4. Connect Local Git to GitHub Repo

Back in terminal:

```bash
git remote add origin <repo.git>
git branch -M main
git push -u origin main
```

✅ Now your project is connected to GitHub.


---

## ❌ If You Ever Want to Disconnect Git

* **Remove Git completely**:

  ```bash
  rm -rf .git
  ```

* **Only remove GitHub connection**:

  ```bash
  git remote remove origin
  ```

---
