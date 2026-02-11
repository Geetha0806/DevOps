## 🔹 Basic Understanding

**What is git commit?**  

`git commit` is used to **save staged changes permanently** into the local repository. It creates a snapshot of the staged files.

**What does a commit contain?**  

A commit contains the following metadata and data:
*   Snapshot of staged files
*   Commit message
*   Author name & email
*   Timestamp
*   Unique commit ID (SHA-1 hash)
*   Reference to the previous commit (parent)

**Basic Syntax:**  

```bash
git commit -m "Commit message"
```

---

## 🔹 Important Variants of git commit

1️⃣ **Commit with Message**  

```bash
git commit -m "Initial commit"
```
This is the most common usage.

2️⃣ **Commit Without Opening Editor (Shortcut)**  

```bash
git commit -m "Fixed bug"
```
This avoids the editor popup.

3️⃣ **Commit All Modified Files (Skip git add)** 

```bash
git commit -a -m "Updated files"
```
Stages and commits only **modified and deleted files**.  

❌ **Note:** This does **NOT** include new untracked files.

4️⃣ **Amend Last Commit (Very Important)**  

```bash
git commit --amend
```
Used to **modify the last commit message** or **add forgotten changes**.  

**Example:**  

```bash
git commit --amend -m "Corrected message"
```

5️⃣ **Amend and Reset Author**  

```bash
git commit --amend --reset-author
```
Used when the author name or email in the last commit was incorrect.

6️⃣ **Commit with Specific Author**  

```bash
git commit --author="Name <email>" -m "Message"
```

7️⃣ **Allow Empty Commit**  

```bash
git commit --allow-empty -m "Trigger build"
```
Commonly used in **CI/CD pipelines** to trigger actions without code changes.

8️⃣ **Sign a Commit (Advanced)**  

```bash
git commit -S -m "Signed commit"
```
Uses **GPG signing** for verified commits.

---

## 🔹 Scenario-Based Interview Questions

1️⃣ **What happens when you run git commit?**  

**Answer:** Git creates a **snapshot of staged files** and saves it in the local repository.

2️⃣ **Does git commit push code to GitHub?**  

**Answer:** **No.** It saves changes locally. You must use `git push` to send them to a remote repository.

3️⃣ **What happens if you run git commit without -m?** 

**Answer:** Git opens the **default text editor** to allow you to write a commit message.

4️⃣ **What is the difference between git commit and git commit -a?**  

| Feature | git commit | git commit -a |
| :--- | :--- | :--- |
| **Files** | Commits staged files only | Automatically stages modified & deleted files |
| **Requirements** | Requires `git add` | Skips `git add` for modified files |
| **New Files** | Does not include new files | Does **NOT** include new files |


5️⃣ **Can you modify a commit after committing?**  

**Answer:** Yes, by using the command `git commit --amend`.

6️⃣ **What is a commit ID?**  

**Answer:** A unique **SHA-1 hash** that identifies a commit (e.g., `a1b2c3d4e5f6...`).

7️⃣ **What is a good commit message practice?**  

**Answer:**  
*   Use clear and meaningful messages.
*   Keep the first line short (under 50 characters).
*   Use **present tense** (e.g., "Fix login bug" instead of "Fixed login bug").

---

## 🔹 Deep Concept Questions

8️⃣ **What is the relationship between commits?**  

**Answer:** Each commit stores a **reference to its parent commit**, forming a linked chain.

9️⃣ **Where are commits stored?**  

**Answer:** Inside the **.git/objects** directory.

## 🔹 Commit Workflow

**Working Directory** → `git add` → **Staging Area** → `git commit` → **Local Repository**
