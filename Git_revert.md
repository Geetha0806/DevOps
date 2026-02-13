## 📌 What is git revert?

`git revert` is used to **undo a specific commit** in shared repositories by creating a new commit that reverses the changes. 

👉 Unlike git reset, it does NOT delete history.
👉 It creates a new commit that reverses the changes.

**Key Characteristics:**

*   Creates a **new commit**.
*   **Safe for shared repositories** because it does not modify existing history.
*   Does **NOT rewrite history**.

### 🔹 Basic Syntax

```bash
git revert commit_id
```

**Example:**

```bash
git revert abc123
```
👉 This creates a new commit that undoes the changes introduced in commit `abc123`.

---

## 🔥 How It Works

Suppose you have the following history:
**A → B → C (HEAD)**

If you run:
```bash
git revert C
```
The new history becomes:
**A → B → C → D (HEAD)**

Where **D** reverses the changes of **C**.
*   ✔️ Original commit **C** still exists.
*   ✔️ History remains intact.

---

## 🔹 Important Variants

1️⃣ **Revert without auto-commit**

```bash
git revert --no-commit commit_id
```
👉 This applies the changes to your working directory and staging area but does **not create the commit immediately**, allowing you to review or add further changes.

2️⃣ **Revert a range of commits**

```bash
git revert OLDER_COMMIT^..NEWER_COMMIT
```

3️⃣ **Revert a merge commit**

```bash
git revert -m 1 merge_commit_id
```
The `-m` flag specifies the **parent number** (which branch to keep). ⚠️ This is a very common interview question.

---

## Interview Questions & Answers

1️⃣ **What is git revert?**

**Answer:** It creates a new commit that reverses the changes introduced by a previous commit.

2️⃣ **Difference between git reset and git revert?**

| Feature | `git reset` | `git revert` |
| :--- | :---: | :---: |
| **Deletes commit** | ✅ | ❌ |
| **Creates new commit** | ❌ | ✅ |
| **Safe for shared repo** | ❌ | ✅ |
| **Rewrites history** | ✅ | ❌ |

3️⃣ **Why is git revert safe in teams?**

**Answer:** Because it does not modify or delete existing history; it simply adds a new commit.

4️⃣ **What happens if we revert a commit that was already pushed?**

**Answer:** It is perfectly safe. You just push the new revert commit normally:
```bash
git push
```
**No force push is required**.

5️⃣ **How do you revert a merge commit?**

**Answer:** 
```bash
git revert -m 1 merge_commit_id
```
The `-m 1` specifies which parent branch's state should be preserved.

6️⃣ **What if a revert causes conflicts?**

**Answer:** You must resolve the conflicts manually, then run:
```bash
git add .
git revert --continue
```
7️⃣ **Can we revert multiple commits?**

**Answer:** Yes, by specifying a range:
```bash
git revert A^..B
```
---

## 🔥 Real Scenario Question

**Q: You pushed a wrong commit to production. What will you use?**

✅ **Correct Answer:**
I will use `git revert` because it is safe and does not rewrite history.

❌ **Avoid saying:**
I will use `git reset --hard` (dangerous in a shared repository).

---

## 🧠 Memory Trick

*   **Reset** → **Remove**
*   **Revert** → **Reverse**

---

## 🚀 Interview Tip (Very Important)

If an interviewer asks: **"Which command is safest to undo changes in production?"** 
Always answer: 👉 **git revert**.
