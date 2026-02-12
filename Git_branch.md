## 🔹 What is git branch?`git branch` is used to **create** a new branch, **list** branches, **delete** branches, **rename** branches, and **manage** branch pointers. A branch in Git is fundamentally just a **pointer to a commit**.

## 🔹 Basic Syntax

```bash
git branch
```
This command lists all local branches.

---

## 🔹 Important Variants of git branch

1️⃣ **List Local Branches**

```bash
git branch
```
The current branch will be indicated with an asterisk `*`.

2️⃣ **List All Branches (Local + Remote)**

```bash
git branch -a
```
Shows both local and remote-tracking branches.

3️⃣ **List Remote Branches Only**

```bash
git branch -r
```
Displays only the branches on the remote repository.

4️⃣ **Create New Branch**

```bash
git branch branch-name
```
This **creates** the branch but does **NOT** switch the working directory to it.

5️⃣ **Create Branch from Specific Commit**

```bash
git branch branch-name commit-id
```
Creates a new branch starting from the specified commit hash.

6️⃣ **Delete Branch (Safe)**

```bash
git branch -d branch-name
```
Performs a safe delete, only removing the branch if it has already been **merged**.

7️⃣ **Force Delete Branch**

```bash
git branch -D branch-name
```
Deletes the branch regardless of its merge status.

8️⃣ **Rename Branch**

To rename the current branch:

```bash
git branch -m new-name
```

To rename a specific branch:

```bash
git branch -m old-name new-name
```

9️⃣ **Show Last Commit of Each Branch**

```bash
git branch -v
```
Provides a more verbose list including the last commit message for each branch.

🔟 **Show Merged Branches**

```bash
git branch --merged
```
Lists branches that have been fully merged into the current branch.

1️⃣1️⃣ **Show Unmerged Branches**

```bash
git branch --no-merged
```
Lists branches that contain changes not yet merged into the current branch.

---

## 🔥 Interview Questions & Answers

1️⃣ **What is a branch in Git?**

**Answer:** A branch is a **lightweight pointer** to a commit that allows for parallel development without affecting the main codebase.

2️⃣ **What happens when you create a branch?**

**Answer:** Git creates a new pointer to the **current commit**. No files are actually copied, making the process very fast and lightweight.

3️⃣ **What is the difference between git branch and git checkout -b?**

| Feature | `git branch` | `git checkout -b` |
| :--- | :--- | :--- |
| **Action** | Creates branch only | Creates and switches to branch |
| **Working Directory** | Does not change | Switches to the new branch |

4️⃣ **What is the difference between -d and -D?**

| Feature | `-d` | `-D` |
| :--- | :--- | :--- |
| **Type** | Safe delete | Force delete |
| **Condition** | Fails if not merged | Deletes regardless |

5️⃣ **What is the default branch in Git?**

**Answer:** Traditionally it was **master**, but it is now commonly referred to as **main**.

6️⃣ **What is a remote tracking branch?**

**Answer:** It is a local reference to a remote branch, such as **origin/main**, which updates whenever you run `git fetch`.

7️⃣ **Is branch creation expensive in Git?**

**Answer:** **No**, because branches are just pointers rather than full copies of files.

---

## 🔥 Advanced Scenario Question

**Why can't I delete a branch using -d?**

**Answer:** Git prevents you from deleting a branch with `-d` if it contains **unmerged changes** to avoid data loss. To bypass this and delete the branch anyway, you must use the force delete command:
```bash
git branch -D branch-name
```
