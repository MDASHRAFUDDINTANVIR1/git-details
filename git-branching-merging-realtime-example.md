# **🚀 Git Branching & Merging: A Real-World Example**

## **👨‍💻 Scenario: 3 Developers Working Together**
### **Team Members:**
- **Alice** (Frontend Developer) → Works on `login-feature` branch.
- **Bob** (Backend Developer) → Works on `fix-homepage-bug` branch.
- **Charlie** (Team Lead) → Manages `main` branch (reviews & merges code).

📌 They are working on a GitHub repository named `project-repo`.

---

## **🚀 Step-by-Step Workflow**  

### **🔹 Step 1: Charlie (Team Lead) Creates the Project**
```bash
# Initialize the repository
git init

# Add files & make the first commit
git add .
git commit -m "Initial project setup"

# Rename branch to main
git branch -M main

# Connect to GitHub
git remote add origin <repo-URL>

# Push to GitHub
git push -u origin main
```

---

### **🔹 Step 2: Alice & Bob Clone the Repository**
```bash
git clone <repo-URL>
cd project-repo
```

---

### **🔹 Step 3: Alice & Bob Create Their Own Branches**
🔹 **Alice (Frontend Developer):**
```bash
git checkout -b login-feature
```
🔹 **Bob (Backend Developer):**
```bash
git checkout -b fix-homepage-bug
```

---

### **🔹 Step 4: Alice & Bob Write Code & Commit Changes**
🔹 **Alice (Login Feature):**
```bash
git add .
git commit -m "Added login form UI"
git push --set-upstream origin login-feature
```
🔹 **Bob (Fixing Homepage Bug):**
```bash
git add .
git commit -m "Fixed homepage loading issue"
git push --set-upstream origin fix-homepage-bug
```

---

### **🔹 Step 5: Charlie (Team Lead) Reviews & Merges the Code**
Charlie pulls the latest updates and merges the branches:
```bash
git checkout main
git pull origin main
git merge login-feature
git merge fix-homepage-bug
```

If conflicts occur, Charlie resolves them, then commits the changes:
```bash
git add .
git commit -m "Resolved merge conflicts"
git push origin main
```

---

### **🔹 Step 6: Alice & Bob Sync Their Branches**
Before starting new work, Alice & Bob sync their branches:
```bash
git checkout main
git pull origin main
git checkout login-feature  # Switch back to their branch
git merge main  # Get latest updates
```

---

## **🎯 Summary of Important Commands**
| Command | Purpose |
|---------|---------|
| `git checkout -b <branch>` | Create and switch to a new branch |
| `git add .` | Add all changes to Git |
| `git commit -m "Message"` | Save changes in the local repo |
| `git push --set-upstream origin <branch>` | Push a new branch to GitHub |
| `git pull origin main` | Get the latest main branch updates |
| `git merge <branch>` | Merge a branch into the current branch |
| `git push origin main` | Push updates to GitHub |

---

## **💡 Final Thoughts**
- **Charlie (Team Lead)** is responsible for merging the code into `main`.
- **Alice & Bob** always **pull the latest `main`** before merging their work.
- **Everyone works in their own branch** to avoid conflicts.

This ensures a smooth and efficient workflow! 🚀✅
