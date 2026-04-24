# Git & GitHub Setup

The local git repo is already initialized and has an initial commit. This doc is the path from "local repo" to "code on GitHub that you push to easily."

## What's done

- `.gitignore` created (excludes .DS_Store, large video files, book PNGs, .env)
- `git init` run on the `Dummy Trading/` folder
- Initial commit made with everything in `_Project Plan/`

## What you need to do — 5 steps

Given you're not a developer, the simplest path is **GitHub Desktop** (GUI, one-click push). Skip the command line entirely.

### Step 1 — Create a GitHub account
If you don't already have one: https://github.com/signup. Free tier is fine. Use your `yutomshazion@gmail.com` email.

### Step 2 — Install GitHub Desktop
https://desktop.github.com. Free. Install, sign in with your GitHub account.

### Step 3 — Add the existing repo
In GitHub Desktop:
- File → Add Local Repository
- Choose: `/Users/tomzion/Desktop/AI Tools/Private/Dummy Trading`
- It will recognize the existing `.git` folder and load everything.

### Step 4 — Publish to GitHub
Click **"Publish repository"** in the top bar.
- Name: `dummy-investor` (or whatever you want)
- Description: "Dummy Investor project — content, book, course, operations"
- **Keep the "Keep this code private" box CHECKED.** This is your business project, not open source.

GitHub Desktop will create the repo on GitHub and push everything up.

### Step 5 — Future pushes
Every time you (or I) edit a file:
- Open GitHub Desktop.
- You'll see the changed files.
- Type a 1-line summary in the "Summary" field (e.g. "Add Reel 001 script").
- Click **Commit to main**.
- Click **Push origin**.

That's it. Three clicks per change.

## Alternative — command line (skip unless you're comfortable)

If you prefer terminal, from the `Dummy Trading` folder:

```bash
# One-time: create the repo on GitHub via website, then:
git remote add origin https://github.com/YOUR_USERNAME/dummy-investor.git
git branch -M main
git push -u origin main

# Every future push:
git add .
git commit -m "your message"
git push
```

This requires authentication setup (SSH key or GitHub CLI `gh auth login`).

## If you want me to help after setup

Once the repo is published, tell me the repo URL and I can help write commit messages, organize branches, and automate things that live inside the repo.
