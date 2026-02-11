1️⃣ **What is git status?**

**Answer:**

`git status` shows the **current state of the working directory and staging area**. It identifies which files are:
*   Untracked
*   Modified
*   Staged
*   Committed

2️⃣ **Why is git status important?**

**Answer:**

It helps developers understand what **changes are pending** before committing.

3️⃣ **Does git status change anything in the repository?**

**Answer:**

No. It is a **read-only command** that only displays information.

---

## 🔹 Output Understanding Questions

4️⃣ **What does “Untracked files” mean?**

**Answer:**

These are files that exist in the working directory but have **not been added to the staging area**.

5️⃣ **What does “Changes not staged for commit” mean?**

**Answer:**

This refers to files that were **modified but not added** using `git add`.

6️⃣ **What does “Changes to be committed” mean?**

**Answer:**

These are files that are **added to the staging area** and are ready for commit.

---

## 🔹 Variants of git status

1️⃣ **git status -s (Short Format)**

❓ **What does git status -s do?**

**Answer:**

Displays output in a **short format**.

**Example:**

```bash
git status -s
```

**Output:**
```bash
M file1.txt
?? file2.txt
```

**Legend:**
*   **M** → Modified
*   **??** → Untracked
*   **A** → Added
*   **D** → Deleted

2️⃣ **git status --short**

Same as `-s`.

3️⃣ **git status -b**

❓ **What does -b do?**

**Answer:**

Shows the **current branch name** along with the status.

**Example:**

```bash
git status -b
```

4️⃣ **git status --branch**

Same as `-b`.

5️⃣ **git status -sb**

❓ **What does -sb do?**

**Answer:**

Shows **short format + branch information**. This is very common in real-world usage.

6️⃣ **git status --ignored**

❓ **What does it do?**

**Answer:**

Shows **ignored files** (defined in `.gitignore`) in the output.
```bash
git status --ignored
```

7️⃣ **git status --untracked-files**

❓ **What does it do?**

**Answer:**

Controls the **display of untracked files**.

**Options:**

```bash
git status --untracked-files=no      # Hides untracked files
git status --untracked-files=normal  # Default behavior
git status --untracked-files=all     # Shows individual files inside untracked directories
```

8️⃣ **git status -u**

**Answer:**
Short version of `--untracked-files`.

**Example:**
```bash
git status -uall
git status -uno
```

---

## 🔹 Scenario-Based Questions

9️⃣ **After modifying a file, what will git status show?**

**Answer:**

It will show the file under **"Changes not staged for commit"**.

🔟 **After running git add file.txt, what will git status show?**

**Answer:**

It will show the file under **"Changes to be committed"**.
```bash
git add file.txt
```

1️⃣1️⃣ **After committing, what will git status show?**

**Answer:**

It will show: **"nothing to commit, working tree clean"**.

---

## 🔹 Deep Understanding Questions

1️⃣2️⃣ **What are the three states shown by git status?**

**Answer:**

1.  **Working directory**
2.  **Staging area**
3.  **Local repository**

1️⃣3️⃣ **How does git status relate to Git architecture?**

**Answer:**

It shows the **differences between** the Working Directory ↔ Staging Area and the Staging Area ↔ Local Repository.

1️⃣4️⃣ **Does git status compare with remote repository?**

**Answer:**

**No**. It compares the local working directory and staging area with the **local repository only**, unless branch tracking information is specifically configured.

---

## 🔹 Advanced Question

1️⃣5️⃣ **Why is git status sometimes slow in large repositories?**

**Answer:**

Because it must **scan the entire working directory** to detect changes.
