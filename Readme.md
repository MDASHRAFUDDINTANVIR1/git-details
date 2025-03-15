# What is Version Control?
Version Control is a system that tracks changes in files over time, allowing multiple people to collaborate, revert to previous versions, and manage updates efficiently.

# What is Git?
Git is a distributed version control system used to track changes in files and collaborate with others on software projects. It helps developers keep track of code history, revert to previous versions, and collaborate seamlessly.

## Step-by-Step Procedure to Set Up Git and GitHub

### 1. **Install Git SCM (Git)**
- Go to the [official Git website](https://git-scm.com/).
- Download the version suitable for your operating system (Windows, macOS, or Linux).
- Follow the installation steps.

**Verify Installation:**
```bash
git --version
```
This should show you the Git version if it’s installed correctly.

---

### 2. **Install Node.js (Optional, for JavaScript-based projects)**
- Go to the [official Node.js website](https://nodejs.org/).
- Download the latest **LTS (Long Term Support)** version.
- Follow the installation steps.

**Verify Installation:**
```bash
node --version
npm --version
```
This should show the version of **Node.js** and **npm** (Node Package Manager).

---

### 3. **Create a New Repository on GitHub**
1. Go to [GitHub](https://github.com/) and create a new account (if you don’t have one).
2. Once logged in, click on the **+** icon at the top right and choose **New repository**.
3. Give your repository a name (e.g., `my-first-repo`), and choose whether it should be **public** or **private**.
4. Click **Create repository**.

---

### 4. **Open VSCode and Set Up Git**
1. **Open VSCode** (Download it from [here](https://code.visualstudio.com/) if you don’t have it).
2. Open the **VSCode terminal** by clicking on `Terminal > New Terminal` from the menu bar.

---

### 5. **Create a Markdown File**
In the terminal, create a `README.md` file:

```bash
touch README.md
```

Open this file in VSCode and add something like:
```markdown
# My First Repository
This is a simple project to learn Git and GitHub.
```

---

### 6. **Initialize Git in Your Project Folder**
In the VSCode terminal, run:

```bash
git init
```

This will initialize Git in your project folder and create a `.git` folder to track all the version control changes.

---

### 7. **Set Up Your Git User**
Set up your **Git username** and **email** (the ones you use for GitHub):

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

---

### 8. **Add and Commit Files to Git**
Stage and commit your files:

1. **Stage** the files (add them to Git):
   ```bash
   git add .
   ```

2. **Commit** the files with a message:
   ```bash
   git commit -m "Initial commit"
   ```

---

### 9. **Link Your Local Repository to GitHub (Remote)**
1. Go to your GitHub repository and copy the repository URL (e.g., `https://github.com/username/my-first-repo.git`).
2. In the VSCode terminal, run:
   ```bash
   git remote add origin https://github.com/username/my-first-repo.git
   ```

---

### 10. **Login to GitHub via VSCode Terminal**
To log in to GitHub through Git on your computer:

1. Run:
   ```bash
   git config --global credential.helper cache
   ```

2. The next time you **push** to GitHub, Git will ask for your **GitHub username and password**.
   
   **For two-factor authentication (2FA):**  
   If you use 2FA on GitHub, you will need to use a **Personal Access Token (PAT)** instead of your password. [Generate a PAT here](https://github.com/settings/tokens).

<br><br>

# Git Command for Projects

| Command | Description |
| ------- | ----------- |
| `git init` | Initialize a local Git repository |
| `git clone ssh://git@github.com/[username]/[repository-name].git` | Create a local copy of a remote repository |

### Basic Snapshotting

| Command | Description |
| ------- | ----------- |
| `git status` | Check status |
| `git add [file-name.txt]` | Add a file to the staging area |
| `git add -A` | Add all new and changed files to the staging area |
| `git commit -m "[commit message]"` | Commit changes |
| `git rm -r [file-name.txt]` | Remove a file (or folder) |
| `git remote -v` | View the remote repository of the currently working file or directory |

### Branching & Merging

| Command | Description |
| ------- | ----------- |
| `git branch` | List branches (the asterisk denotes the current branch) |
| `git branch -a` | List all branches (local and remote) |
| `git branch [branch name]` | Create a new branch |
| `git branch -d [branch name]` | Delete a branch |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git checkout -b [branch name]` | Create a new branch and switch to it |
| `git checkout -b [branch name] origin/[branch name]` | Clone a remote branch and switch to it |
| `git branch -m [old branch name] [new branch name]` | Rename a local branch |
| `git checkout [branch name]` | Switch to a branch |
| `git checkout -` | Switch to the branch last checked out |
| `git checkout -- [file-name.txt]` | Discard changes to a file |
| `git merge [branch name]` | Merge a branch into the active branch |
| `git merge [source branch] [target branch]` | Merge a branch into a target branch |
| `git stash` | Stash changes in a dirty working directory |
| `git stash clear` | Remove all stashed entries |
| `git stash pop` | Apply latest stash to working directory |

### Sharing & Updating Projects

| Command | Description |
| ------- | ----------- |
| `git push origin [branch name]` | Push a branch to your remote repository |
| `git push -u origin [branch name]` | Push changes to remote repository (and remember the branch) |
| `git push` | Push changes to remote repository (remembered branch) |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git pull` | Update local repository to the newest commit |
| `git pull origin [branch name]` | Pull changes from remote repository |
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git` | Add a remote repository |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH |

### Inspection & Comparison

| Command | Description |
| ------- | ----------- |
| `git log` | View changes |
| `git log --summary` | View changes (detailed) |
| `git log --oneline` | View changes (briefly) |
| `git diff [source branch] [target branch]` | Preview changes before merging |
  
<br>

# 🚀 Fixing GitHub Pages Not Working Due to Missing `index.html`

When using **GitHub Pages**, it looks for an `index.html` file as the homepage. If your repository doesn't have `index.html`, your website may not load properly. Below are solutions to fix this issue.

## ✅ Solution 1: Rename `demo.html` to `index.html`

If your repository has a file like `demo.html`, but **GitHub Pages is not working**, rename it to `index.html` using Git.

### 📌 Steps:

1. **Rename the File Using Git Command:**
   ```bash
   git mv demo.html index.html
   ```

2. **Commit the Changes:**
   ```bash
   git commit -m "Renamed demo.html to index.html"
   ```

3. **Push the Changes to GitHub:**
   ```bash
   git push origin main
   ```

4. **Check Your GitHub Pages Link:**  
   Now, visit your GitHub Pages link:
   ```
   https://<your-username>.github.io/<repository-name>/
   ```
   Your website should load properly with `index.html` as the main page.

---

## ✅ Solution 2: Use a Folder in GitHub Pages (e.g., `docs` Folder)

You can store your HTML file inside a folder (like `docs`) and set GitHub Pages to use that folder.

### 📌 Steps:

1. **Create a Folder and Move Your HTML File:**
   ```bash
   mkdir docs
   mv index.html docs/
   ```

2. **Commit and Push the Changes:**
   ```bash
   git add .
   git commit -m "Moved index.html to docs folder"
   git push origin main
   ```

3. **Change GitHub Pages Settings:**
   - Go to **Settings** in your repository.
   - Scroll down to **GitHub Pages**.
   - Under **Source**, select **`docs/` folder**.

4. **Check Your GitHub Pages Link:**
   ```
   https://<your-username>.github.io/<repository-name>/
   ```

Now, your website will load the `index.html` file from the `docs` folder.

---

## ✅ Solution 3: Use a Custom File Name in GitHub Pages URL

If you **don't want to rename your file** but still want to access it, you need to **manually specify the file name** in the URL.

### 📌 Steps:

1. **Ensure Your File Exists in the Repository**  
   Example: If your file is `demo.html`, it should be visible in your repository.

2. **Access the File Using This URL:**
   ```
   https://<your-username>.github.io/<repository-name>/demo.html
   ```

Now, your file will open directly without renaming it.

---

## ✅ Solution 4: Using a `gh-pages` Branch (For Deployed Projects)

For **React, Angular, Vue, or other built projects**, it’s best to use a `gh-pages` branch.

### 📌 Steps:

1. **Create a `gh-pages` Branch:**
   ```bash
   git checkout -b gh-pages
   ```

2. **Commit Your `index.html` in `gh-pages` Branch:**
   ```bash
   git add .
   git commit -m "Set up gh-pages branch with index.html"
   git push origin gh-pages
   ```

3. **Enable GitHub Pages for `gh-pages` Branch:**
   - Go to **Settings > GitHub Pages**.
   - Select **`gh-pages`** as the source.

4. **Check Your GitHub Pages Link:**
   ```
   https://<your-username>.github.io/<repository-name>/
   ```

Now, your site will load properly.

---

## 🔥 Conclusion

| Solution | When to Use |
|----------|------------|
| **Rename `demo.html` to `index.html`** | If GitHub Pages is not loading your file. |
| **Use `docs/` Folder** | If you want a cleaner repo structure. |
| **Use a Custom File URL** | If you don't want to rename `demo.html`. |
| **Use `gh-pages` Branch** | If working with frameworks like React. |

### 📢 If GitHub Pages Still Doesn't Work:
- **Wait a few minutes** – sometimes it takes time to update.
- **Clear browser cache** (`Ctrl + Shift + R`).
- **Make sure your repository is public** (GitHub Pages doesn't work for private repos unless you have a Pro account).
- **Check GitHub Pages settings** to ensure it's enabled.

---

Now, you're all set to fix GitHub Pages issues! 🚀✨

