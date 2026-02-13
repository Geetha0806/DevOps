## 📌 What is git merge?

`git merge` is used to combine changes from one branch into another branch. 

*   👉 It integrates branch history.
*   👉 It does **NOT** rewrite history.
*   👉 It is safe for shared repositories.

It takes the changes from a source branch and merges them into the current branch.

### 🔹 Basic Syntax

```bash
git merge branch_name
```

**Example:**

```bash
git checkout main
git merge feature
```
👉 Merges `feature` into `main`.

## 🔥 How Merge Works

Suppose:
*   **main:** A → B → C
*   **feature:** D → E

After merge:
*   **main:** A → B → C → **M**

✔️ **M** = merge commit.
✔️ History is preserved.

## 🔹 Types of Merge (Very Important)

1️⃣ **Fast-Forward Merge**

Happens when the `main` branch has no new commits.
*   **Before:** `A → B` (main) and `C → D` (feature).
*   **After merge:** `A → B → C → D`.
*   ✔️ No merge commit created.
*   ✔️ Simple pointer move.

2️⃣ **Three-Way Merge**

Happens when both branches have new commits.
*   ✔️ Creates merge commit.
*   ✔️ Most common type.

## 🔹 Important Variants

1️⃣ **Force merge commit (no fast-forward)**

```bash
git merge --no-ff branch_name
```
Creates a merge commit even if a fast-forward is possible.

2️⃣ **Abort merge**

```bash
git merge --abort
```
Used when a conflict happens.

3️⃣ **Squash merge**

```bash
git merge --squash branch_name
```
*   ✔️ Combines all commits into one.
*   ✔️ Does not create a merge commit.

## 🔥 Merge Conflicts

Occurs when the **same file** and **same lines** are modified in both branches.

**Resolution:**

1.  Fix conflict manually.
2.  ```bash
    git add .
    ```
3.  ```bash
    git commit
    ```

## Interview Questions & Answers

1️⃣ **What is git merge?**

**Answer:** It combines changes from one branch into another branch.

2️⃣ **What are the types of merge?**

**Answer:** Fast-forward merge and Three-way merge.

3️⃣ **What is fast-forward merge?**

**Answer:** When no new commits exist in the target branch, Git just moves the pointer forward.

4️⃣ **What is three-way merge?**

**Answer:** When both branches have new commits, Git creates a merge commit.

5️⃣ **Does merge rewrite history?**

**Answer:** No.

6️⃣ **Is merge safe for shared branches?**

**Answer:** Yes.

7️⃣ **Difference between merge and rebase?**

| Feature | Merge | Rebase |
| :--- | :---: | :---: |
| **Creates merge commit** | ✅ | ❌ |
| **Rewrites history** | ❌ | ✅ |
| **Linear history** | ❌ | ✅ |
| **Safe for shared branch** | ✅ | ❌ |


8️⃣ **What is squash merge?**

**Answer:** It combines all commits from a branch into a single commit before merging.

## 🔥 Real Interview Scenario

**Q: Which method is safer in team projects?**

**Answer:** 👉 `git merge`.

**Q: Which method keeps history clean?**

**Answer:** 👉 `git rebase`.

## 🧠 Memory Trick

*   **Merge** = Join branches.
*   **Rebase** = Replay commits.

## 🚀 Final Interview Tip

If an interviewer asks: **"Why do companies prefer merge in production?"**
**Answer:** 
*   Because it **preserves history**.
*   **No rewriting** of history.
*   **Safer collaboration**.
