### 📌 What is git reflog?

`git reflog` is used to track every movement of **HEAD** in your local repository. It acts as a safety net, helping you recover from mistakes that might otherwise seem permanent.

**Reflog** stands for **Reference Log**. It records:
*   Branch switches
*   Resets
*   Rebases
*   Commits
*   Merges

⚠️ **Note:** It is **local only** and is not shared with the remote repository.

### 🔹 Basic Syntax

```bash
git reflog
```

**Example output:**

```text
abc123 HEAD@{0}: reset: moving to HEAD~1
def456 HEAD@{1}: commit: added login feature
ghi789 HEAD@{2}: checkout: moving from main to feature
```
---

### 🔥 Why Is It Important?

Even if you perform a `git reset --hard`, your commit is still recoverable using the reflog.

#### 🔹 Recover Deleted Commit (Very Important)

1.  **Step 1:** Run the reflog command:
    ```bash
    git reflog
    ```
2.  **Step 2:** Copy the required **commit ID**.
3.  **Step 3:** Perform a hard reset to that ID:
    ```bash
    git reset --hard commit_id
    ```
🎉 **Commit restored!**

#### 🔹 Restore Deleted Branch

If a branch was deleted, find the last commit of that branch in the reflog and run:
```bash
git checkout -b branch_name commit_id
```

#### 🔹 Additional Variants

*   **Reflog for a specific branch:**
*   
    ```bash
    git reflog branch_name
    ```
*   **Show reflog with local dates:**
*   
    ```bash
    git reflog --date=local
    ```
---

### Interview Questions & Answers

1️⃣ **What is git reflog?**  

**Answer:** It records all movements of **HEAD** in the local repository.

2️⃣ **Can we recover from git reset --hard?**  

**Answer:** **Yes**, by using `git reflog`.

3️⃣ **Is reflog shared with remote?** 

**Answer:** **No**. It is local to your machine only.

4️⃣ **How long does reflog keep history?**  

**Answer:** By default, it keeps history for **90 days** for normal commits and **30 days** for unreachable commits.

5️⃣ **Difference between git log and git reflog?**

| Feature | git log | git reflog |
| :--- | :---: | :---: |
| **Shows commit history** | ✅ | ❌ |
| **Shows HEAD movement** | ❌ | ✅ |
| **Shows deleted commits** | ❌ | ✅ |
| **Local only** | ❌ | ✅ |


6️⃣ **When do we use reflog?**  

**Answer:** Use it after an accidental hard reset, a wrong rebase, after deleting a branch, or to recover any lost commits.

---

### 🔥 Real Interview Scenario

**Q: You accidentally ran `git reset --hard HEAD~1`. Can you recover?**  
**Correct Answer:** Yes. I would run `git reflog` to find the previous commit ID and then use `git reset --hard previous_commit_id` to restore the state.

### 🧠 Memory Trick

*   **Log** = Commit history
*   **Reflog** = HEAD history
