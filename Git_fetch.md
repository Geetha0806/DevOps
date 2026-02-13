## 📌 What is git fetch?

`git fetch` is used to **download changes** from a remote repository without merging them into your current work. It is considered the **safe way** to check for remote updates before integrating them.

*   **Downloads** the latest commits from a remote repository.
*   **Updates** remote-tracking branches (e.g., `origin/main`).
*   Does **NOT** change your working directory.
*   Does **NOT** merge automatically.

### 🔹 Basic Syntax

```bash
git fetch
```
Running this is equivalent to running `git fetch origin`.

**To fetch a specific branch:**

```bash
git fetch origin main
```

---

## 🔥 How It Works

Suppose your repository history looks like this:
*   **Remote:** `A → B → C`
*   **Local:** `A → B`

After running `git fetch`, your local repository state becomes:
*   **Your branch:** `A → B` (remains unchanged)
*   **Remote-tracking branch (`origin/main`):** Points to `C`

**What changes after fetch?**

It updates remote-tracking branches like `origin/main` or `origin/feature`, but it does **NOT** update your local `main` or `feature` branches.

---

## 🔥 Important Variants

1️⃣ **Fetch All Remotes**

```bash
git fetch --all
```
Downloads updates from all registered remote repositories.

2️⃣ **Prune Deleted Remote Branches**

```bash
git fetch --prune
```
Removes local references to branches that have been deleted in the remote repository.

3️⃣ **Dry Run**

```bash
git fetch --dry-run
```
Shows what changes would be fetched without actually downloading them.

4️⃣ **Fetch Tags**

```bash
git fetch --tags
```
Downloads tags from the remote repository.

---

## 🔥 Fetch vs Pull (Very Important)

| Feature | `git fetch` | `git pull` |
| :--- | :---: | :---: |
| **Downloads changes** | ✅ | ✅ |
| **Merges automatically** | ❌ | ✅ |
| **Safe** | ✅ | ⚠️ |
| **Modifies working directory** | ❌ | ✅ |

---

## 🎯 Interview Questions & Answers

1️⃣ **What is git fetch?**

**Answer:** It downloads changes from a remote repository without merging them.

2️⃣ **What happens after git fetch?**

**Answer:** Remote-tracking branches like `origin/main` get updated, but your local branches remain unchanged.

3️⃣ **Why is fetch considered safer than pull?**

**Answer:** Because it does not automatically merge changes into your active branch, preventing potential conflicts or unwanted history changes until you are ready.

4️⃣ **How do you merge changes after fetch?**

**Answer:** 
```bash
git fetch
git merge origin/main
```

5️⃣ **Does fetch affect the working directory?**

**Answer:** No.

6️⃣ **When should we prefer fetch over pull?**

**Answer:** 
*   In team environments.
*   Before reviewing remote changes.
*   To avoid unwanted merge commits.

---

## 🔥 Real Interview Scenario

**Q: You want to check remote updates before merging. What will you use?**

**Correct answer:** 
1.  Run `git fetch`.
2.  Review changes with `git log origin/main`.

---

## 🧠 Memory Trick

*   **Fetch** = Bring data.
*   **Pull** = Bring + Apply.

## 🚀 Final Interview Tip

If an interviewer asks for the **best practice in team collaboration**, answer that you should use `git fetch`, review the changes, and then **merge manually**.
