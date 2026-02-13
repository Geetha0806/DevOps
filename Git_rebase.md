## 📌 What is git rebase?

`git rebase` is used to reapply commits on top of another base branch.

*   👉 It **rewrites history**.
*   👉 It creates a **linear commit history**.
*   👉 Very common interview topic.

It moves or reapplies commits from one branch onto another branch. Instead of merging branches with a merge commit, rebase replays commits on top of the latest base branch.

### 🔹 Basic Syntax

```bash
git rebase branch_name
```

---

## 🔥 How It Works (Important)

**Suppose:**
*   **main:** A → B → C
*   **feature:** D → E (HEAD)

If you run (while on **feature**):
```bash
git rebase main
```

**Git will:**

1.  Remove **D** and **E** temporarily.
2.  Move **feature** to **C**.
3.  Replay **D** and **E** on top.

**Result:**

*   **main:** A → B → C
*   **feature:** D' → E'
*   ✔️ **New commit hashes**
*   ✔️ **Linear history**
*   ❌ **No merge commit**

---

## 🔹 Important Variants

1️⃣ **Interactive Rebase (Most Important)**

```bash
git rebase -i HEAD~3
```
Used to:
*   Edit commit messages
*   Squash commits (combine multiple into one)
*   Reorder commits
*   Delete commits

2️⃣ **Rebase onto specific branch**

```bash
git rebase main
```

3️⃣ **Continue after conflict**

```bash
git rebase --continue
```

4️⃣ **Abort rebase**

```bash
git rebase --abort
```

5️⃣ **Skip problematic commit**

```bash
git rebase --skip
```

---

## 🔥 Rebase vs Merge (Interview Favorite)

| Feature | Merge | Rebase |
| :--- | :---: | :---: |
| **Creates merge commit** | ✅ | ❌ |
| **Linear history** | ❌ | ✅ |
| **Rewrites history** | ❌ | ✅ |
| **Safe for shared branch** | ✅ | ❌ |

---

## 🎯 Interview Questions & Answers

1️⃣ **What is git rebase?**

**Answer:** It reapplies commits from one branch onto another base branch to create a linear history.

2️⃣ **What is the main difference between merge and rebase?**

**Answer:** Merge creates a merge commit, while rebase rewrites history to keep it linear.

3️⃣ **Why is rebase considered dangerous?**

**Answer:** Because it rewrites commit history and changes commit hashes.

4️⃣ **When should we NOT use rebase?**

**Answer:** On shared or public branches like `main`.

5️⃣ **What is interactive rebase?**

**Answer:** It is a mode that allows editing, squashing, deleting, or reordering commits.

6️⃣ **What is squash in rebase?**

**Answer:** Combining multiple commits into one. In `git rebase -i HEAD~3`, you would change `pick` to `squash`:
```bash
pick abc123
squash def456
```

7️⃣ **What happens if a conflict occurs?**

**Answer:** Resolve the conflict, then run:
```bash
git add .
git rebase --continue
```

8️⃣ **What happens to commit hashes after rebase?**

**Answer:** They change.

---

## 🔥 Real Interview Scenario

**Q: Your feature branch is outdated. What will you use?**

**Correct Answer:**
1.  ```bash
    git checkout feature
    ```
2.  ```bash
    git rebase main
    ```
3.  Then use a force push (but not a normal push):

    ```bash
    git push --force-with-lease
    ```

---

## 🧠 Memory Trick

*   **Merge** = Join history
*   **Rebase** = Rewrite history

## 🚀 Very Important Interview Tip

- If an interviewer asks which workflow gives a **clean history**, the answer is the **Rebase workflow**. 
- If they ask which is **safer for team collaboration**, the answer is **Merge**.
