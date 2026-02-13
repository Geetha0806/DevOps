## 🔹 Basic Usage

1️⃣ **Switch to an existing branch**

```bash
git checkout branch_name
```
👉 Moves **HEAD** to the specified branch.

2️⃣ **Create and switch to a new branch**

```bash
git checkout -b new_branch
```
👉 Creates a branch and switches to it simultaneously.

3️⃣ **Create branch from a specific commit**

```bash
git checkout -b new_branch commit_id
```
Initializes a new branch at a specific point in history.

4️⃣ **Checkout a specific commit (Detached HEAD)**

```bash
git checkout commit_id
```
👉 **HEAD** points directly to a commit instead of a branch reference.

5️⃣ **Restore a file from the last commit**

```bash
git checkout -- file.txt
```
👉 Discards local changes made to that file.

6️⃣ **Restore file from a specific commit**

```bash
git checkout commit_id -- file.txt
```
Retrieves the version of a file from a specific historical snapshot.

7️⃣ **Switch to the previous branch**

```bash
git checkout -
```
Quickly toggles back to the branch you were previously on.

8️⃣ **Force checkout (discard local changes)**

```bash
git checkout -f branch_name
```
Switches branches while discarding any local changes permanently.

---

## 🔥 Important Concept: HEAD

**HEAD** is the pointer to the current branch. 
*   **When on a branch:** It points to the branch reference.
*   **When detached:** It points directly to a specific commit.

---

## 🔹 Interview Questions & Answers

1️⃣ **What is git checkout used for?**

**Answer:** It is used to switch branches, create new branches, restore files, or move **HEAD** to a specific commit.

2️⃣ **What is Detached HEAD state?**

**Answer:** It occurs when we checkout a specific commit instead of a branch (e.g., `git checkout abc123`), meaning **HEAD** is no longer attached to a branch.

3️⃣ **How do you create and switch branch in one command?**

**Answer:** Use `git checkout -b feature_branch`.

4️⃣ **Difference between git checkout branch and git checkout -b branch?**

| Command | Purpose |
| :--- | :--- |
| `git checkout branch` | Switch to an existing branch |
| `git checkout -b branch` | Create and switch to a new branch |

5️⃣ **What happens if you checkout with uncommitted changes?**

**Answer:** Git prevents switching if changes conflict; you must commit them, stash them, or use `-f` to force the switch.

6️⃣ **How to discard local file changes?**

**Answer:** Use `git checkout -- file.txt`.

7️⃣ **How to recover from detached HEAD?**

**Answer:** Switch back to a branch using `git checkout branch_name` or create a new branch from that point using `git checkout -b new_branch`.

8️⃣ **What is the modern alternative to git checkout?**

| Old Command | Modern Replacement |
| :--- | :--- |
| `git checkout branch` | `git switch branch` |
| `git checkout -b branch` | `git switch -c branch` |
| `git checkout -- file` | `git restore file` |

9️⃣ **What does git checkout - do?**

**Answer:** It switches to the previously checked-out branch.

🔟 **What is the risk of git checkout -f?**

**Answer:** It discards all local changes permanently.
