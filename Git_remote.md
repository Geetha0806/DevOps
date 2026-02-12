## 🔹 What is git log?

**git log** is used to view the **commit history** of a repository. It displays essential information including the **Commit ID (SHA)**, **Author**, **Date**, and **Commit message**.

## 🔹 Basic Command

```bash
git log
```
This command shows the **full detailed commit history**. You can press **q** to exit the view.

---

## 🔹 Important Variants of git log

1️⃣ **One-Line Format (Very Common)**

```bash
git log --oneline
```
Shows a **short commit ID** and the **commit message** on a single line.

2️⃣ **Show Limited Number of Commits**

```bash
git log -n 5
```
*or*
```bash
git log --max-count=5
```
Shows the **last 5 commits**.

3️⃣ **Graph View (Very Important)**

```bash
git log --oneline --graph
```
Displays the **branch structure visually**.

4️⃣ **Show Specific Author**

```bash
git log --author="Geetha"
```
Filters commits by a **specific author**.

5️⃣ **Show Commits for Specific File**

```bash
git log file.txt
```
Shows the history of **that file only**.

6️⃣ **Show Changes (Diff) with Log**

```bash
git log -p
```
Shows the **patch/diff** for each commit.

7️⃣ **Compact Format**

```bash
git log --pretty=oneline
```
Displays a compact version of the log.

8️⃣ **Custom Format (Advanced)**

```bash
git log --pretty=format:"%h - %an, %ar : %s"
```
Useful for **scripting** purposes.

9️⃣ **Show Stats**

```bash
git log --stat
```
Shows the **number of insertions and deletions** per commit.

🔟 **Show Commits Since Date**

```bash
git log --since="2 days ago"
```
*or*
```bash
git log --since="2025-01-01"
```
Filters commits based on a **starting date**.

1️⃣1️⃣ **Show Commits Between Dates**

```bash
git log --since="2025-01-01" --until="2025-02-01"
```
Filters commits within a **specific date range**.

1️⃣2️⃣ **Show Branch-Specific Log**

```bash
git log branch-name
```
Shows the log for a **specific branch**.
---

## 🔹 Scenario-Based Interview Questions

1️⃣ **What does git log show?**

**Answer:** It shows the **commit history of the current branch**.

2️⃣ **How do you see a compact version of commit history?**

**Answer:**

```bash
git log --oneline
```


3️⃣ **How do you see commit history in graphical format?**

**Answer:**

```bash
git log --oneline --graph
```

4️⃣ **How do you check who made changes?**

**Answer:**

```bash
git log --author="Name"
```

5️⃣ **How do you see changes introduced in a commit?**

**Answer:**

```bash
git log -p
```

6️⃣ 
**How do you view history of a single file?**
**Answer:**

```bash
git log filename
```
---

## 🔹 Deep Understanding Questions

7️⃣ **What is the commit ID shown in git log?**

**Answer:** It is a **unique SHA-1 hash** that identifies each individual commit.

8️⃣ **Does git log show remote commits?**

**Answer:** It shows commits available in your **local repository**. To see remote updates, you must **fetch** them first.

9️⃣ **What is HEAD in git log?**

**Answer:** **HEAD** points to the **latest commit** of the current branch.
