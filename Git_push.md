## 🔹 What is git push?

`git push` is used to **upload local commits to a remote repository** (e.g., GitHub). It transfers commits from your **Local Repository** to the **Remote Repository**.,

## 🔹 Basic Syntax

```bash
git push <remote> <branch>
```

**Example:**

```bash
git push origin main
```

---

## 🔹 Important Variants of git push

1️⃣ **Basic Push**

```bash
git push origin main
```
Pushes the local `main` branch to the remote `origin`.

2️⃣ **Push with Upstream Tracking (Very Important)**

```bash
git push -u origin main
```
Sets the **upstream tracking branch**. After running this once, you can simply use:
```bash
git push
```

3️⃣ **Push All Branches**

```bash
git push --all
```
Pushes all local branches to the remote repository.

4️⃣ **Push Tags**

```bash
git push --tags
```
Pushes all tags to the remote repository.

5️⃣ **Force Push (Very Important & Risky)**

```bash
git push --force
```
*or*
```bash
git push -f
```
**Overwrites remote history.** ⚠ This is dangerous in team environments.

6️⃣ **Safer Force Push**

```bash
git push --force-with-lease
```
This is safer than `--force` because it checks if the remote has changed before overwriting, preventing you from unintentionally overwriting others' work.,

7️⃣ **Push to Different Branch Name**

```bash
git push origin local-branch:remote-branch
```
**Example:**

```bash
git push origin feature:dev
```

8️⃣ **Delete Remote Branch**

```bash
git push origin --delete branch-name
```

9️⃣ **Push Specific Tag**

```bash
git push origin v1.0
```

---

## 🔹 Scenario-Based Interview Questions

1️⃣ **What does git push do?**

**Answer:** It uploads local commits to the remote repository.

2️⃣ **What is the difference between git commit and git push?**

| Feature | git commit | git push |
| :--- | :--- | :--- |
| **Action** | Saves changes locally | Uploads changes to remote |
| **Impact** | Affects local repo | Affects remote repo |

3️⃣ **What does -u mean in git push -u?**

**Answer:** It sets the **upstream (tracking) branch**, so future pushes and pulls can be done using just `git push` or `git pull`.

4️⃣ **What happens if the remote has new commits and you try to push?**

**Answer:** The push will be **rejected**. You must `pull` or `fetch` and `merge` those changes first.

5️⃣ **When should you use --force?**

**Answer:** Usually after **rewriting history** (e.g., after a `git rebase`). However, it should be avoided on shared branches.

6️⃣ **What is the difference between --force and --force-with-lease?**

| Feature | --force | --force-with-lease |
| :--- | :--- | :--- |
| **Behavior** | Overwrites remote blindly | Checks if remote changed first |
| **Risk Level** | High / Risky | Lower / Safer |

7️⃣ **Can you push without specifying a branch?**

**Answer:** Yes, if the **upstream tracking** has already been set.
```bash
git push
```

8️⃣ **What does “Everything up-to-date” mean?**

**Answer:** It means your local and remote branches are already synchronized.

---

## 🔹 Deep Understanding Questions

9️⃣ **What protocols does Git use to push?**

**Answer:** **HTTPS** and **SSH**.

🔟 **Where is upstream tracking information stored?**

**Answer:** It is stored in the **.git/config** file.

---

## 🔹 Common Errors

❌ **Rejected Push**
```text
! [rejected] main -> main (non-fast-forward)
```
*   **Reason:** The remote repository contains new commits that you do not have locally.
*   **Solution:**
    ```bash
    git pull origin main
    ```
