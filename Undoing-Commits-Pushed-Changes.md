## **1️⃣ Viewing Recent Commits and Commit Hashes**

To see the **most recent commit** with its **commit hash**, use:

### **🔹 Show Last Commit (Full Details)**
```sh
git log -1
```
✅ Example Output:
```
commit a1b2c3d4e5f6g7h8i9j0k (HEAD -> main)
Author: Alice <alice@example.com>
Date:   Tue Mar 18 10:00:00 2025 +0600

    Fixed homepage layout issue
```
📌 **Commit hash:** `a1b2c3d4e5f6g7h8i9j0k`

### **🔹 Show Last Commit in One Line**
```sh
git log --oneline -1
```
✅ Example Output:
```
a1b2c3d Fixed homepage layout issue
```

### **🔹 Show Last Commit with Changes**
```sh
git show --summary
```
✅ Example Output:
```
commit a1b2c3d4e5f6g7h8i9j0k (HEAD -> main)
Author: Alice <alice@example.com>
Date:   Tue Mar 18 10:00:00 2025 +0600

    Fixed homepage layout issue

diff --git a/index.html b/index.html
...
```

---

## **2️⃣ Undoing Commits and Pushed Changes**

### **Situation 1: Undo a Commit BEFORE Pushing (Local Repository Only)**

🔹 **Scenario:** A developer has made changes, staged them (`git add .`), and committed (`git commit -m "Changes"`) but hasn’t pushed yet. Now, they want to go back to the previous version.

| **Option** | **What Happens?** | **Command to Use** |
| --- | --- | --- |
| 🔹 **Undo Commit & Keep Changes in Staging** | The commit is removed, but changes stay in staging. | `git reset --soft HEAD~1` |
| 🔹 **Undo Commit & Discard Changes Completely** | The commit is removed, and changes are permanently deleted. | `git reset --hard HEAD~1` |

---

### **Situation 2: Undo a Commit AFTER Pushing (GitHub Repository)**

🔹 **Scenario:** A developer has already pushed the changes (`git push origin fix-bug`) and now wants to **remove the commit from GitHub** and **go back to the previous version.**

| **Option** | **What Happens?** | **Command to Use** |
| --- | --- | --- |
| 🔹 **Undo & Delete from GitHub and Local Repository** | The commit is removed **from both GitHub and local**. | 1️⃣ `git reset --hard HEAD~1`  
2️⃣ `git push --force origin fix-bug` |
| 🔹 **Undo & Keep Changes Locally** | The commit is removed **from GitHub**, but changes remain in the code editor. | 1️⃣ `git reset --soft HEAD~1`  
2️⃣ `git push --force origin fix-bug` |

---

## **3️⃣ Quick Summary of Solutions**

| **Scenario** | **Best Solution** | **Command** |
| --- | --- | --- |
| Undo a local commit before pushing & keep changes | `git reset --soft HEAD~1` |  |
| Undo a local commit before pushing & delete changes | `git reset --hard HEAD~1` |  |
| Undo a pushed commit & remove from GitHub | `git reset --hard HEAD~1` → `git push --force` |  |
| Undo a pushed commit & keep changes locally | `git reset --soft HEAD~1` → `git push --force` |  |

⚠ **Warning:** `git push --force` rewrites history and can cause issues if others are working on the same branch.

🚀 **Best Practice:** Use `git revert <commit-hash>` if working in a team to avoid conflicts.

