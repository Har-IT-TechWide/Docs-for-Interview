Here’s a comprehensive list of common **Git interview questions** along with detailed explanations and example scenarios.

---

### **1. What is Git, and how does it differ from other version control systems?**  
#### **Explanation:**
Git is a **distributed version control system (DVCS)** that allows multiple developers to work on a project simultaneously. Unlike centralized version control systems like SVN, Git does not rely on a single central repository. Instead, each developer has a local copy of the repository, which provides **better performance, offline work, and redundancy**.

#### **Example Scenario:**
- In a **centralized VCS** (like SVN), a developer must be connected to the main repository to commit changes.  
- In **Git**, developers can commit locally and later push the changes to a remote repository.

---

### **2. What are the basic Git commands every developer should know?**
#### **Explanation:**
Here are some essential Git commands:

| Command | Description |
|---------|------------|
| `git init` | Initializes a new Git repository. |
| `git clone <repo-url>` | Clones a repository from a remote source. |
| `git add <file>` | Stages a file for commit. |
| `git commit -m "message"` | Commits changes with a message. |
| `git push origin <branch>` | Pushes changes to the remote repository. |
| `git pull origin <branch>` | Fetches and merges updates from the remote repository. |
| `git status` | Shows the current status of the working directory. |
| `git log` | Displays commit history. |

#### **Example Scenario:**
To initialize a repository and push changes:
```sh
git init
git add .
git commit -m "Initial commit"
git remote add origin <repo-url>
git push -u origin main
```

---

### **3. What is the difference between `git merge` and `git rebase`?**
#### **Explanation:**
- **`git merge`**: Combines the history of two branches while maintaining separate commit histories.
- **`git rebase`**: Moves a feature branch on top of another branch to keep a linear commit history.

#### **Example Scenario:**
- If a feature branch (`feature-1`) is behind the `main` branch, you can:
  - Use **merge** to create a merge commit:
    ```sh
    git checkout feature-1
    git merge main
    ```
  - Use **rebase** to move `feature-1` commits on top of `main`:
    ```sh
    git checkout feature-1
    git rebase main
    ```

---

### **4. How do you resolve merge conflicts in Git?**
#### **Explanation:**
Merge conflicts occur when Git cannot automatically combine changes from two branches. You must manually edit conflicting files.

#### **Steps to Resolve a Merge Conflict:**
1. **Attempt to merge**:
   ```sh
   git merge feature-branch
   ```
2. **If a conflict occurs**, Git marks the conflicting areas.
3. **Manually edit the conflicting files** and resolve the issues.
4. **Mark files as resolved**:
   ```sh
   git add <resolved-file>
   ```
5. **Commit the changes**:
   ```sh
   git commit -m "Resolved merge conflict"
   ```

#### **Example Scenario:**
If `file.txt` has different changes in `main` and `feature-branch`, Git will show:
```plaintext
<<<<<<< HEAD
Code from main branch
=======
Code from feature branch
>>>>>>> feature-branch
```
You manually update the file to resolve the conflict.

---

### **5. What are Git branching strategies, and which one should you use?**
#### **Explanation:**
Branching strategies help teams manage code efficiently.

#### **Common Strategies:**
1. **Feature Branching** - Each feature gets a dedicated branch.
2. **Git Flow** - Uses `develop`, `feature`, `release`, and `hotfix` branches.
3. **GitHub Flow** - Simpler approach using `main` and feature branches.
4. **Trunk-Based Development** - Developers work on `main` with short-lived feature branches.

#### **Example Scenario:**
In **Git Flow**, a developer:
```sh
git checkout -b feature-xyz develop
# Work on the feature
git push origin feature-xyz
```

---

### **6. How do you revert a commit in Git?**
#### **Explanation:**
You can undo changes using different commands based on the scenario.

| Command | Description |
|---------|------------|
| `git revert <commit-hash>` | Creates a new commit that undoes a previous commit. |
| `git reset --hard <commit-hash>` | Resets the branch to a previous state, discarding changes. |
| `git reset --soft <commit-hash>` | Moves the HEAD but keeps changes staged. |

#### **Example Scenario:**
To undo the last commit but keep changes:
```sh
git reset --soft HEAD~1
```
To completely remove changes:
```sh
git reset --hard HEAD~1
```

---

### **7. What is the difference between `git fetch` and `git pull`?**
#### **Explanation:**
- **`git fetch`**: Downloads updates from the remote but does not merge them.
- **`git pull`**: Downloads and automatically merges updates.

#### **Example Scenario:**
```sh
git fetch origin
git merge origin/main  # Manually merge changes
```
or simply:
```sh
git pull origin main  # Fetches and merges automatically
```

---

### **8. How do you create and delete a Git branch?**
#### **Explanation:**
| Command | Description |
|---------|------------|
| `git branch <branch-name>` | Creates a new branch. |
| `git checkout <branch-name>` | Switches to a branch. |
| `git checkout -b <branch-name>` | Creates and switches to a new branch. |
| `git branch -d <branch-name>` | Deletes a local branch. |
| `git push origin --delete <branch-name>` | Deletes a remote branch. |

#### **Example Scenario:**
```sh
git checkout -b feature-xyz
git push origin feature-xyz
```
To delete:
```sh
git branch -d feature-xyz
git push origin --delete feature-xyz
```

---

### **9. How do you track changes in a specific file over time?**
#### **Explanation:**
Use `git log` with file options.
```sh
git log -- <file>
```
To see line-by-line changes:
```sh
git blame <file>
```

---

### **10. How do you set up a Git repository for a new project?**
#### **Explanation:**
1. **Initialize the repo**:
   ```sh
   git init
   ```
2. **Add a remote origin**:
   ```sh
   git remote add origin <repo-url>
   ```
3. **Create a `.gitignore` file**:
   ```sh
   echo "node_modules/" > .gitignore
   ```
4. **Make an initial commit**:
   ```sh
   git add .
   git commit -m "Initial commit"
   git push -u origin main
   ```

---

### **Final Thoughts**
These questions cover **Git fundamentals, branching, merging, conflict resolution, and best practices**. Would you like me to add scenario-based problem-solving questions as well? 🚀