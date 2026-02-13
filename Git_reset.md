## What is git reset?

`git reset` is one of the most powerful and dangerous Git commands.

**It is used to:**

*   Unstage files
*   Move HEAD
*   Delete commits
*   Rewrite history

### 🧠 What Does git reset Do?

It moves the **HEAD pointer** to a specific commit. Depending on the option used, it can affect:
*   Local Repository
*   Staging Area
*   Working Directory

### 🔹 Basic Syntax

```bash
git reset [mode] commit_id
```
---

### 🔥 Three Important Modes (Most Asked in Interviews)

1️⃣ **--soft (Safest Reset)**

```bash
git reset --soft commit_id
```
**What happens?**

*   HEAD moves.
*   Staging area remains.
*   Working directory remains.
*   **Commits are removed** but **changes stay staged**.
*   ✅ **Use case:** Used when you want to rewrite a commit message.

2️⃣ **--mixed (Default Mode)**

```bash
git reset commit_id
```
*or*
```bash
git reset --mixed commit_id
```
**What happens?**

*   HEAD moves.
*   Staging area is cleared.
*   Working directory remains unchanged.
*   **Changes become unstaged**.

3️⃣ **--hard (Most Dangerous)**

```bash
git reset --hard commit_id
```
**What happens?**

*   HEAD moves.
*   Staging area is cleared.
*   Working directory is cleared.
*   ⚠️ **All changes are lost permanently**.

---

### 🔹 Reset a Single File (Unstage)

```bash
git reset file.txt
```
*   Removes file from the staging area.
*   Working directory remains unchanged.
*   **Modern alternative:** 
```bash
git restore --staged file.txt
```

---

### 🔥 Visual Understanding

Suppose we have the following history:

**Commit A → Commit B → Commit C (HEAD)**

If we run:
```bash
git reset --soft B
```
**Result:**

**Commit A → Commit B (HEAD)**
Commit C disappears, but the changes from C remain staged.

---

### Interview Questions & Answers

**1️⃣ What is git reset?**

**Answer:** It moves the HEAD pointer to a specified commit and optionally modifies the staging area and working directory.

**2️⃣ What are the three types of reset?**

**Answer:**

| Mode | Affects Repo | Affects Staging | Affects Working Dir |
| :--- | :---: | :---: | :---: |
| `--soft` | ✅ | ❌ | ❌ |
| `--mixed` | ✅ | ✅ | ❌ |
| `--hard` | ✅ | ✅ | ✅ |

**3️⃣ What is the default reset mode?**

**Answer:** `--mixed`.

**4️⃣ When should we use --soft?**

**Answer:** When we want to modify the last commit but keep the changes staged.

**5️⃣ Why is --hard dangerous?**

**Answer:** Because it permanently deletes uncommitted changes.

**6️⃣ Difference between git reset and git revert?**

| Feature | git reset | git revert |
| :--- | :---: | :---: |
| **Deletes commit** | ✅ | ❌ |
| **Safe for shared repo** | ❌ | ✅ |
| **Creates new commit** | ❌ | ✅ |
| **Rewrites history** | ✅ | ❌ |

**7️⃣ Can we recover from a hard reset?**

**Answer:** Sometimes yes, using `git reflog` if the commit reference still exists.

**8️⃣ What happens if you reset after pushing to remote?**

**Answer:** It is ⚠️ **dangerous**. You must use `git push --force`, which can break the history for the rest of the team.

---

### 🔥 Advanced Interview Question
**Q: What is the difference between git reset --hard and git checkout?**
**Answer:** `git reset --hard` moves HEAD backward and deletes commits, whereas `git checkout` switches branches or restores files. `checkout` does not delete commit history.

---

### 🧠 Memory Trick

Think:
*   **Soft** → Safe
*   **Mixed** → Medium
*   **Hard** → Hazard

### 🚀 Real Interview Tip

If an interviewer asks: **"Which command is safest to undo a commit in a shared repo?"**
**Answer:** Use `git revert`. Avoid `git reset --hard`.
