## 🔹 What is git diff?

**git diff** is used to compare changes between different states of your project, including:
*   **Working Directory**
*   **Staging Area**
*   **Local Repository (commits)**
*   **Branches**

It provides a line-by-line comparison of these differences.

## 🔹 Basic Command

```bash
git diff
```
**What does it show?**  

It shows the difference between the **Working Directory ↔ Staging Area**, specifically displaying unstaged changes.

---

## 🔹 Important Variants of git diff

1️⃣ **Compare Staging Area with Last Commit**  

```bash
git diff --staged
```
*or*  
```bash
git diff --cached
```
Shows the difference between the **Staging Area ↔ Last Commit**.

2️⃣ **Compare Two Commits**  

```bash
git diff commit1 commit2
```
Example:  
```bash
git diff a1b2c3 d4e5f6
```
Compares two specific snapshots in history.

3️⃣ **Compare Two Branches**  

```bash
git diff branch1 branch2
```
Example:  
```bash
git diff main feature
```
Shows the differences between two branches.

4️⃣ **Compare Specific File**  

```bash
git diff file.txt
```
Shows changes made to a single file.

5️⃣ **Compare Specific File Between Commits**  

```bash
git diff commit1 commit2 -- file.txt
```
Isolates the changes for one file across two different points in time.

6️⃣ **Show Only File Names Changed**  

```bash
git diff --name-only
```
Lists only the names of files that have differences.

7️⃣ **Show File Status (Added/Modified/Deleted)**  

```bash
git diff --name-status
```

**Output example:**  

*   `M file1.txt` (Modified)
*   `A file2.txt` (Added)
*   `D file3.txt` (Deleted)

8️⃣ **Word-Level Difference**  

```bash
git diff --word-diff
```
Shows changes at the **word level** instead of the line level.

9️⃣ **Show Difference Between Local and Remote** 

```bash
git diff origin/main
```
Shows changes between local and remote (typically used after running `git fetch`).

---

## 🔹 Understanding Diff Output

**Legend:**  

*   `-` → removed line  
*   `+` → added line

---

## 🔹 Scenario-Based Interview Questions

1️⃣ **What does git diff show?**  

**Answer:** It shows the difference between the working directory and the staging area.

2️⃣ **How do you see staged changes?** 

**Answer:** Use `git diff --staged`.

3️⃣ **What is the difference between git diff and git log?**  

| git diff | git log |
| :--- | :--- |
| Shows line-by-line comparison | Shows snapshot history |
| Compares current changes | Shows commit history |

4️⃣ **How do you compare two branches?** 

**Answer:** Use `git diff branch1 branch2`.

5️⃣ **How do you compare two commits?**  

**Answer:** Use `git diff commit1 commit2`.

6️⃣ **How do you check what will be committed before running commit?**  

**Answer:** Use `git diff --staged`.

---

## 🔹 Deep Understanding Questions

7️⃣ **Does git diff show committed history?**  

**Answer:** **No.** It compares changes between different states. To view history, you should use `git log`.

8️⃣ **Why is git diff important in real projects?**  

**Answer:** It is essential for:

*   Reviewing changes before a commit.
*   Debugging issues.
*   Comparing branches.
*   Validating merges.
