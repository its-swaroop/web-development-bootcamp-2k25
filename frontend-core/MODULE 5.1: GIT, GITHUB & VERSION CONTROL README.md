# MODULE 5.1: GIT, GITHUB & VERSION CONTROL

#### 1. Using Git for Version Control and Collaboration

* Git is a **distributed version control system**
* Tracks code changes over time
* Enables multiple developers to work without conflict

**Basic Git Workflow:**

```bash
git init                     # Initialize repo
git add .                    # Stage changes
git commit -m "message"      # Commit snapshot
```

**Collaboration Benefits:**

* Track who changed what, when, and why
* Revert to previous versions easily
* Manage and merge features from teammates

---

#### 2. Git Forking, Branching, Cloning

**Forking (on GitHub):**

* Create your own copy of someone else's repository
* Useful for open source contribution

**Cloning:**

```bash
git clone https://github.com/username/repo.git
```

**Branching:**

```bash
git branch feature-xyz        # Create branch
git checkout feature-xyz      # Switch to branch
```

**Modern Combined:**

```bash
git switch -c feature-xyz     # Create and switch
```

**Merging:**

```bash
git checkout main
git merge feature-xyz
```

---

#### 3. Using GitHub as a Remote Repository

**Connect local repo to GitHub:**

```bash
git remote add origin https://github.com/user/repo.git
git push -u origin main       # First push
```

**Subsequent pushes:**

```bash
git add .
git commit -m "update"
git push
```

**Pull updates from remote:**

```bash
git pull
```

---

#### 4. Checkout and Rolling Back Changes

**Undo changes (safe):**

```bash
git checkout -- filename     # Revert file to last commit
```

**Stash changes temporarily:**

```bash
git stash
git stash pop
```

**Roll back commit:**

```bash
git revert <commit-id>       # Create inverse commit
git reset --hard <commit-id> # Danger: resets to old state
```

---

#### 5. Using Git and GitHub with Xcode (iOS Context)

* Xcode has built-in Git integration
* Use Source Control menu to:

  * Commit, push, pull, merge
  * Create branches
* View history directly in IDE
* Ideal for versioning Swift and React Native code

---

### Summary

| Task                  | Command or Tool                        |
| --------------------- | -------------------------------------- |
| Initialize repo       | `git init`                             |
| Stage and commit      | `git add`, `git commit`                |
| Clone                 | `git clone`                            |
| Branching             | `git branch`, `git checkout`, `switch` |
| Push to GitHub        | `git remote add`, `git push`           |
| Revert or reset       | `git checkout`, `git reset`, `revert`  |
| Xcode Git integration | Source Control tab (GUI)               |

<footer>TO BE CONT...</footer>
