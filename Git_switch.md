## 📌 What is git switch?

`git switch` is a modern Git command used exclusively for **branch operations**. It was introduced to reduce the confusion caused by `git checkout`, which previously handled both branch switching and file restoration.

**Key Characteristics:**

*   Used only for **switching and creating branches**.
*   **Cannot** restore or checkout specific files.
*   Provides a **cleaner and more readable** alternative to `git checkout`.

---

## 🔹 Basic Syntax

1️⃣ **Switch to an existing branch**

```bash
git switch branch_name
```
👉 Moves your working directory to the specified branch.

2️⃣ **Create and switch to a new branch**

```bash
git switch -c new_branch
```
👉 The `-c` flag stands for **create**.

3️⃣ **Create branch from a specific commit**

```bash
git switch -c new_branch commit_id
```
👉 Starts a new branch from a historical snapshot.

4️⃣ **Switch to the previous branch**

```bash
git switch -
```
👉 Quickly toggles back to the last branch you were on.

5️⃣ **Force switch (discard conflicts)**

```bash
git switch -f branch_name
```
👉 Switches branches even if there are local conflicts, discarding them.

6️⃣ **Create a tracking branch from remote**

```bash
git switch -c branch_name origin/branch_name
```
*OR automatically track:*
```bash
git switch --track origin/branch_name
```
👉 Sets up a local branch to track a remote counterpart.

---

## 🔥 Important Concepts

✅ **Branch Focus Only**

Unlike `git checkout`, `git switch` cannot:
*   Restore files.
*   Checkout specific files.
*   Restore deleted files.

✅ **Improved Clarity**

Using `git switch feature` instead of `git checkout feature` makes the intent of the command explicit and prevents accidental file restoration.

---

## Interview Questions & Answers

1️⃣ **What is git switch?**

**Answer:** It is a modern Git command used strictly for switching between branches and creating new ones.

2️⃣ **Why was git switch introduced?**

**Answer:** Because `git checkout` had multiple purposes (switching branches AND restoring files), which often caused confusion for users. `git switch` separates the branch-related operations into their own command.

3️⃣ **What is the difference between git checkout and git switch?**

| Feature | `git checkout` | `git switch` |
| :--- | :--- | :--- |
| **Switch branch** | ✅ | ✅ |
| **Create branch** | ✅ | ✅ |
| **Restore files** | ✅ | ❌ |
| **Safer usage** | ❌ | ✅ |
| **Clear purpose** | ❌ | ✅ |

4️⃣ **What happens if you have uncommitted changes?**

**Answer:** Git will prevent the switch if the changes conflict with the target branch. You must either **commit** the changes, **stash** them, or use the `-f` flag to **force** the switch and discard conflicts.

5️⃣ **Can git switch move to a specific commit (detached HEAD)?**

**Answer:** Yes, but you must explicitly use the `--detach` flag:
```bash
git switch --detach commit_id
```
👉 This moves the repository into a **detached HEAD** state.

6️⃣ **How do you track a remote branch?**

**Answer:** You can use the `--track` flag:
```bash
git switch --track origin/feature
```
---

## 🧠 Memory Trick

*   **switch** → branches only.
*   **restore** → files only.
*   **Clear separation** = easier learning and safer usage.

## 🚀 Real Interview Tip

If an interviewer asks which command should be preferred in modern Git:
*   **Use `git switch`** for branch switching.
*   **Use `git restore`** for file restoration.
*   **Avoid overusing `git checkout`** for these tasks.
