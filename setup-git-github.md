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

2. **Commit** the files with a message and select main branch:
   ```bash
   git commit -m "Initial commit"
   git branch -M main
   ```

---

### 9. **Link Your Local Repository to GitHub (Remote) & push the code in main branch**
1. Go to your GitHub repository and copy the repository URL (e.g., `https://github.com/username/my-first-repo.git`).
2. In the VSCode terminal, run:
   ```bash
   git remote add origin https://github.com/username/my-first-repo.git
   git push -u origin main
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
