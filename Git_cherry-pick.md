## 📌 What is git cherry-pick?

`git cherry-pick` is used to **apply a specific commit** from one branch to another branch. Instead of merging the whole branch, you selectively pick only the commit you want.

**Key Characteristics:**

*   **Copies a commit** from one branch to another.
*   **Applies it** to the current branch.
*   **Creates a new commit** with a unique hash.
*   Used for **selective changes**.

## 🔹 Basic Syntax

```bash
git cherry-pick commit_id
```

**Example:**

```bash
git cherry-pick abc123
```
👉 Applies commit `abc123` to the current branch.

---

## 🔥 How It Works

Suppose you have the following history:

*   **Branch A:** A → B → C
*   **Branch B:** A → D → E (HEAD)

If you are on **Branch B** and run `git cherry-pick C`, the result is:
**Branch B: A → D → E → C'**

*   **C'** is a copy of commit **C**.
*   A **new commit hash** is created for the copy.

---

## 🔹 Important Variants

1️⃣ **Cherry-pick without auto-commit**

```bash
git cherry-pick --no-commit commit_id
```
👉 Applies the changes to the working directory but does not create the commit automatically.

2️⃣ **Cherry-pick multiple commits**

```bash
git cherry-pick commit1 commit2
```

3️⃣ **Cherry-pick a range**

```bash
git cherry-pick A^..B
```

4️⃣ **Continue after resolving conflicts**

```bash
git cherry-pick --continue
```

5️⃣ **Abort the operation**

```bash
git cherry-pick --abort
```
---

## 🎯 Interview Questions & Answers

1️⃣ **What is the difference between merge and cherry-pick?**

| Feature | Merge | Cherry-pick |
| :--- | :---: | :---: |
| **Moves entire branch** | ✅ | ❌ |
| **Select specific commit** | ❌ | ✅ |
| **Creates merge commit** | Usually | ❌ |
| **Copies commit** | ❌ | ✅ |


2️⃣ **Does cherry-pick create a new commit?**

**Answer:** Yes. It creates a new commit with a new hash.

3️⃣ **What happens if there is a conflict?**

**Answer:** You must resolve the conflict, then run:
```bash
git add .
git cherry-pick --continue
```

4️⃣ **When should we use cherry-pick?**

**Answer:**
*   **Hotfixes** from production branches.
*   **Selective bug fixes**.
*   Applying a **specific feature** without merging the full branch.

5️⃣ **Can cherry-pick cause duplicate commits?**

**Answer:** **Yes**, because it copies the commit rather than moving it.

6️⃣ **Is cherry-pick safe in shared repositories?**

**Answer:** Yes, but it should be used carefully as it can create a duplicate history if misused.

---

## 🔥 Real Interview Scenario

**Q: You fixed a bug in main, but need the same fix in the release branch. What will you do?**

**Answer:** 
1.  Switch to the target branch:
    ```bash
    git checkout release
    ```
2.  Pick the specific fix:
    ```bash
    git cherry-pick commit_id
    ```
---

## 🚀 Advanced Interview Question

**Q: What is the risk of cherry-pick?**
*   **Duplicate commits** in the history.
*   **History becomes messy** and harder to track.

---

## 🔥 Quick Comparison

| Command | Purpose |
| :--- | :--- |
| **merge** | Combine branches |
| **rebase** | Reapply commits |
| **cherry-pick** | Copy specific commit |


## 🧠 Memory Trick

Think: **Cherry-pick = Pick only the cherry 🍒 (specific commit)**.
