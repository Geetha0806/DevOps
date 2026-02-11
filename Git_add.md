1️⃣ **What is git add?**

**Answer:**

`git add` is used to move changes from the working directory to the **staging area (index)**. It prepares files for commit.

2️⃣ **Does git add commit the changes?**

**Answer:**

**No**. It only stages the changes. The commit happens using `git commit`.

3️⃣ **Why do we need git add?**

**Answer:**

Because Git follows a **two-step commit process**:
1.  Stage changes (`git add`)
2.  Commit changes (`git commit`)

This allows for **selective commits**.

---

## 🔹 Core Variants of git add

1️⃣ **Add a Specific File**

```bash
git add file.txt
```
Stages only that file.

2️⃣ **Add Multiple Files**

```bash
git add file1.txt file2.txt
```

3️⃣ **Add All Files in Current Directory**

```bash
git add .
```
Stages **new, modified, and deleted files** specifically inside the current directory.

4️⃣ **Add All Files in Repository**

```bash
git add -A
```
Stages **everything** across the entire repository.

5️⃣ **Add Only Modified & Deleted (Not New Files)**

```bash
git add -u
```
Stages modified and deleted files but **does NOT stage new untracked files**.

6️⃣ **Add Only New & Modified (Not Deletions)**

```bash
git add *
```
Not always recommended as it is shell dependent.

7️⃣ **Interactive Add (Very Important)**

```bash
git add -i
```
Interactive staging mode that allows you to stage specific files or hunks and review changes.

8️⃣ **Patch Mode (Very Important in Interviews)**

```bash
git add -p
```
Allows staging **specific parts (hunks)** of a file, which is useful for partial commits and maintaining a clean history.

9️⃣ **Force Add Ignored Files**

```bash
git add -f file.log
```
Adds a file even if it is listed in `.gitignore`.

---

## 🔹 Scenario-Based Questions

🔟 **After modifying a file, what happens when you run git add?**

**Answer:**

The modified version moves to the **staging area**.

1️⃣1 **If you modify a file after staging it, what happens?**

**Answer:**

Git will show **one version staged** and **one version modified but not staged**. You must run `git add` again to stage the latest changes.

1️⃣2️⃣ **What is the difference between git add . and git add -A?**

**Answer:**

| Feature | git add . | git add -A |
| :--- | :--- | :--- |
| **Scope** | Current directory | Entire repository |
| **Deletions** | May not stage deletions outside current path | Stages everything |

1️⃣3️⃣ **What is the difference between git add -A and git add -u?**

**Answer:**

| Feature | git add -A | git add -u |
| :--- | :--- | :--- |
| **Changes** | Adds new + modified + deleted | Adds only modified + deleted |
| **Untracked** | Includes untracked files | Does NOT include untracked files |

---

## 🔹 Deep Understanding Question

1️⃣4️⃣ **Where are staged changes stored?**

**Answer:**

In the **staging area (index)** inside the `.git` directory.

1️⃣5️⃣ **Can you unstage a file after git add?**

**Answer:**

Yes. Use the following commands:

```bash
git restore --staged file.txt
```
Or the older way:
```bash
git reset file.txt
```
