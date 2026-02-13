## 📌 What is git restore?

`git restore` is a modern Git command used to:
*   **Restore files**
*   **Discard changes**
*   **Unstage files**
*   **Restore files from a specific commit**

**Note:** It does **NOT** switch branches.

---

## 🔹 Basic Syntax

1️⃣ **Discard local changes (working directory)**

```bash
git restore file.txt
```
👉 Reverts the file to the last committed version.

2️⃣ **Restore all modified files**

```bash
git restore .
```

3️⃣ **Unstage a file (move from staging to working area)**

```bash
git restore --staged file.txt
```
👉 This is equivalent to:
```bash
git reset file.txt
```

4️⃣ **Restore file from a specific commit**

```bash
git restore --source=commit_id file.txt
```

5️⃣ **Restore both staged and working directory**

```bash
git restore --source=HEAD --staged --worktree file.txt
```
---

## 🔥 Important Flags

| Option | Meaning |
| :--- | :--- |
| `--staged` | Restore from staging area |
| `--worktree` | Restore in working directory |
| `--source=` | Specify commit to restore from |

---

## 🧠 How It Works (Architecture View)

Git has three areas, and `git restore` moves files between these areas safely:
1.  **Working Directory**
2.  **Staging Area (Index)**
3.  **Local Repository (.git)**

---

## 🎯 Interview Questions & Answers

1️⃣ **What is git restore?**  

**Answer:** It is a modern Git command used to restore files or discard changes safely.

2️⃣ **Why was git restore introduced?**  

**Answer:** To **separate file restoration from branch switching**. Previously, `git checkout` handled both, which caused confusion.

3️⃣ **How do you discard local changes?**  

```bash
git restore file.txt
```

4️⃣ **How do you unstage a file?**  
```bash
git restore --staged file.txt
```

5️⃣ **Difference between git reset and git restore --staged?**  

| Command | Purpose |
| :--- | :--- |
| `git reset file.txt` | Unstage file |
| `git restore --staged file.txt` | Unstage file (modern way) |

6️⃣ **Can git restore recover deleted files?**  

**Answer:** **Yes**, if the file exists in the last commit:
```bash
git restore deleted_file.txt
```

7️⃣ **Is git restore dangerous?**  

**Answer:** It can be, because running `git restore file.txt` **permanently discards uncommitted changes**.

8️⃣ **Can we restore from an old commit?**  

**Answer:** **Yes**:
```bash
git restore --source=abc123 file.txt
```
---

## 🔥 Common Confusion (Interview Favorite)

**Q: What is the difference between git checkout, git switch, and git restore?**

| Command | Purpose |
| :--- | :--- |
| `git checkout` | Old command (handles both branch and file operations) |
| `git switch` | Branch operations only |
| `git restore` | File operations only |

---

## 🧠 Memory Trick

*   **Switch** → Branch
*   **Restore** → File
*   **Clear separation** = Modern Git

---

## 🚀 Real Interview Tip

If an interviewer asks how to safely discard changes:
*   **For files** → Use `git restore`
*   **For branch switching** → Use `git switch`
*   **Avoid using `git checkout`** in modern Git workflow.
