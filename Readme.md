# What is Version Control?
Version Control is a system that tracks changes in files over time, allowing multiple people to collaborate, revert to previous versions, and manage updates efficiently.

# What is Git?
Git is a distributed version control system used to track changes in files and collaborate with others on software projects. It helps developers keep track of code history, revert to previous versions, and collaborate seamlessly.

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

