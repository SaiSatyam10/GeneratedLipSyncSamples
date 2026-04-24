# GitHub Pages Deployment Plan
# Project: GeneratedLipSyncSamples

> Drop this file in the root of your `GeneratedLipSyncSamples` folder.
> At each step marked **[ASK CLAUDE]**, paste that exact prompt to Claude and follow its guidance.

---

## What we are building

A public website at `https://saisatyamjena.github.io/GeneratedLipSyncSamples/`
that shows side-by-side video dubbing demos (original video + driving audio → dubbed result).

---

## Folder structure you need to create on your machine

Before touching GitHub, your local folder should look exactly like this:

```
GeneratedLipSyncSamples/          ← root folder (this is the repo)
├── plan.md                       ← this file
├── index.html                    ← copy from MuseTalkDemo/Githubio_code/
├── style.css                     ← copy from MuseTalkDemo/Githubio_code/
├── demos.js                      ← copy from MuseTalkDemo/Githubio_code/
└── assets/
    ├── ex1/
    │   ├── raw_ex1.mp4
    │   ├── audio_ex1.wav
    │   └── dubbed_output _ex1.mp4
    ├── ex2/
    │   ├── raw_ex2.mp4
    │   ├── audio_ex2.wav
    │   └── dubbed_output_ex2.mp4
    └── ex3/                      ← add when you have example 3
        ├── raw_ex3.mp4
        ├── audio_ex3.wav
        └── dubbed_output_ex3.mp4
```

---

## Step 1 — Install Git on your Mac

**What:** Git is the tool that sends your files to GitHub.

**Check if you already have it:**
Open Terminal (press Cmd+Space, type "Terminal", hit Enter) and run:
```
git --version
```

- If you see something like `git version 2.x.x` → you already have it, skip to Step 2.
- If you see an error or a popup asking to install → follow the popup and install.

**[ASK CLAUDE if stuck]:**
> "I tried running `git --version` in Terminal and got this: [paste what you see]. What should I do?"

---

## Step 2 — Create the GitHub repository

**What:** You are creating an empty online home for your files.

1. Go to https://github.com and log in to your account (`saisatyamjena`).
2. Click the **+** button in the top-right → **New repository**.
3. Fill in:
   - **Repository name:** `GeneratedLipSyncSamples`
   - **Description:** `MuseTalk lip-sync demo samples`
   - **Visibility:** Public  ← important, must be public for free GitHub Pages
   - **Do NOT** tick "Add a README file" (leave everything unchecked)
4. Click **Create repository**.
5. GitHub shows you a page with setup instructions — **leave this tab open**, you will need the URL shown there (looks like `https://github.com/saisatyamjena/GeneratedLipSyncSamples.git`).

**[ASK CLAUDE if stuck]:**
> "I created the repo but I'm not sure what URL to use. The page shows me this: [paste what GitHub shows]. What's my next step?"

---

## Step 3 — Set up the local folder

**What:** You create the folder on your Mac that will become the repo.

1. In Finder, go to a location you like (Desktop, Documents, wherever).
2. Create a new folder named exactly: `GeneratedLipSyncSamples`
3. Copy these files **into** that folder:
   - `index.html` from `MuseTalkDemo/Githubio_code/`
   - `style.css` from `MuseTalkDemo/Githubio_code/`
   - `demos.js` from `MuseTalkDemo/Githubio_code/`
   - This `plan.md` file
4. Inside the folder, create a subfolder called `assets`.
5. Inside `assets`, create subfolders `ex1`, `ex2`, etc.
6. Copy your media files into each example subfolder (see structure above).

**[ASK CLAUDE if stuck]:**
> "I'm trying to set up the folder structure for GeneratedLipSyncSamples. Can you confirm which files go where given my MuseTalkDemo folder is at [your path]?"

---

## Step 4 — Initialize git and push to GitHub

**What:** You link your local folder to GitHub and upload everything.

Open Terminal. Run these commands **one line at a time**, pressing Enter after each:

```bash
cd ~/Desktop/GeneratedLipSyncSamples
```
*(Change the path if your folder is somewhere else — e.g. `~/Documents/GeneratedLipSyncSamples`)*

```bash
git init
```

```bash
git add .
```

```bash
git commit -m "initial site with demo samples"
```

```bash
git branch -M main
```

```bash
git remote add origin https://github.com/saisatyamjena/GeneratedLipSyncSamples.git
```

```bash
git push -u origin main
```

The last command will ask for your GitHub username and password.
**Note:** GitHub no longer accepts your account password here. You need a **Personal Access Token** instead.

**[ASK CLAUDE for the token]:**
> "git push is asking for my password but my GitHub password doesn't work. How do I create a Personal Access Token and use it here? I'm on a Mac."

**[ASK CLAUDE if push fails]:**
> "When I ran `git push -u origin main` I got this error: [paste the error]. What should I do?"

---

## Step 5 — Enable GitHub Pages

**What:** You flip the switch that makes GitHub serve your files as a website.

1. Go to your repo on GitHub: `https://github.com/saisatyamjena/GeneratedLipSyncSamples`
2. Click **Settings** (top tab bar of the repo).
3. In the left sidebar, click **Pages**.
4. Under **Source**, select:
   - Branch: `main`
   - Folder: `/ (root)`
5. Click **Save**.
6. Wait about 60 seconds, then refresh the page.
7. A green banner will appear with your live URL:
   `https://saisatyamjena.github.io/GeneratedLipSyncSamples/`

**[ASK CLAUDE if stuck]:**
> "I went to Settings → Pages but I don't see the option to pick a branch. This is what I see: [screenshot or description]. What's wrong?"

---

## Step 6 — Verify the site works

1. Open the URL in your browser: `https://saisatyamjena.github.io/GeneratedLipSyncSamples/`
2. You should see the dark-themed page with your demo cards.
3. Check that videos play and audio plays.

**Common issues and what to tell Claude:**

| Problem | What to say to Claude |
|---|---|
| Page loads but videos are broken | "Videos don't load on my GitHub Pages site. The asset paths in demos.js are [paste them]. My folder structure is [describe it]." |
| Whole page is blank or 404 | "I get a 404 at my GitHub Pages URL. I enabled Pages on the main branch root. Here is what my repo root looks like: [list files]." |
| Page looks broken / no styling | "The page loads but has no styling. style.css is in the root next to index.html. Here is my index.html link tag: [paste line]." |

---

## Step 7 — Adding a new example in the future

Every time you have a new dubbing sample:

1. Create a new subfolder in `assets/` (e.g. `assets/ex3/`).
2. Drop the three files in: `raw_exN.mp4`, `audio_exN.wav`, `dubbed_output_exN.mp4`.
3. Open `demos.js` in any text editor and add a new block (copy an existing one and edit).
4. Run these three Terminal commands from inside your repo folder:

```bash
git add .
git commit -m "add example 3"
git push
```

The site updates automatically within ~30 seconds.

**[ASK CLAUDE if stuck adding an example]:**
> "I want to add example 3 to my GeneratedLipSyncSamples GitHub Pages site. My new files are named [list them]. Can you write the demos.js block I need to add and confirm the folder structure?"

---

## Quick reference — Terminal commands cheat sheet

| What you want to do | Command |
|---|---|
| Go into the repo folder | `cd ~/Desktop/GeneratedLipSyncSamples` |
| See what files git knows about | `git status` |
| Stage all changes | `git add .` |
| Save a snapshot with a message | `git commit -m "your message here"` |
| Upload to GitHub | `git push` |
| See recent commits | `git log --oneline` |

---

## File ownership summary

| File | Purpose | Edit frequency |
|---|---|---|
| `demos.js` | List of examples shown on the page | Every time you add a sample |
| `index.html` | Page structure | Rarely (only for layout changes) |
| `style.css` | Visual design | Rarely (only for design changes) |
| `assets/exN/` | Your video and audio files | Every time you add a sample |
| `plan.md` | This guide | Never (keep for reference) |
