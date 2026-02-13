## 📌 What is git pull?

`git pull` is used to fetch changes from a remote repository and merge them into your current branch.

👉 It is a combination of:
```bash
git fetch + git merge
```

It performs two main actions:
*   **Downloads** the latest changes from the remote.
*   **Automatically merges** them into the current branch.

### 🔹 Basic Syntax

```bash
git pull
```
**Equivalent to:**

```bash
git fetch
git merge
```

### 🔹 Pull from Specific Remote & Branch

```bash
git pull origin main
```
*   **origin** → remote name
*   **main** → branch name

---

## 🔥 How It Works

Suppose:
*   **Remote:** `A → B → C`
*   **Local:** `A → B`

After running `git pull`, the local branch becomes: `A → B → C`.

---

## 🔹 Important Variants

1️⃣ **Pull with Rebase**

```bash
git pull --rebase
```
**Equivalent to:**

```bash
git fetch
git rebase
```
*   ✔️ Keeps history linear.
*   ✔️ No merge commit.

2️⃣ **Force Pull (Overwrite local changes)**

```bash
git fetch
git reset --hard origin/main
```
⚠️ **Dangerous** – deletes local changes.

3️⃣ **Pull Only (No auto-commit)**

```bash
git pull --no-commit
```


4️⃣ **Set Upstream Branch**

First time:
```bash
git branch --set-upstream-to=origin/main
```
After that, you can simply run:
```bash
git pull
```
---

## 🔥 Pull vs Fetch (Interview Favorite)

| Feature | git fetch | git pull |
| :--- | :---: | :---: |
| **Downloads changes** | ✅ | ✅ |
| **Automatically merges** | ❌ | ✅ |
| **Safer** | ✅ | ❌ |
| **Recommended in teams** | ✅ | ⚠️ Careful |

---

## 🎯 Interview Questions & Answers

1️⃣ **What is git pull?**

**Answer:** It fetches changes from a remote repository and merges them into the current branch.

2️⃣ **What commands does git pull internally execute?**

**Answer:** `git fetch` + `git merge`.

3️⃣ **Difference between git pull and git fetch?**

**Answer:** Fetch only downloads changes. Pull downloads and merges automatically.

4️⃣ **What is git pull --rebase?**

**Answer:** It fetches changes and rebases your local commits on top of the remote branch.

5️⃣ **When should we use --rebase?**

**Answer:** When you want a clean history and wish to avoid merge commits.

6️⃣ **What happens if a conflict occurs during pull?**

**Answer:** Resolve the conflict, then run:
```bash
git add .
git commit
```
**OR if using rebase:**

```bash
git rebase --continue
```


7️⃣ **Is git pull safe in teams?**

**Answer:** It can cause unexpected merge commits. Many teams prefer running `git fetch` and `git merge` separately.

---

## 🔥 Real Interview Scenario

**Q: You want to update your branch but avoid merge commits. What will you use?**

**Correct answer:** 
```bash
git pull --rebase
```
---

## 🧠 Memory Trick

Think:
*   **Fetch** = Download
*   **Pull** = Download + Merge

---

## 🚀 Important Interview Tip

**If an interviewer asks: "Why is git pull sometimes discouraged?"**

**Answer:** Because it automatically merges changes and may create unexpected merge commits.
