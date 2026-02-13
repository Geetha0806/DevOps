## 🔹 Basic Understanding

**git tag** is used to mark a specific commit with a label.

**Mostly used for:**

*   **Version releases**
*   **Production deployments**
*   **Milestones**

**Examples:** `v1.0`, `v2.1`, `release-2026`.

---

## 📌 What is a Tag?

A tag is a reference to a **specific commit** and acts as a **permanent marker**. Unlike branches, tags do **NOT** move automatically; they stay fixed to one commit.

---

## 🔹 Types of Tags (Very Important)

1️⃣ **Lightweight Tag**

```bash
git tag v1.0
```
*   Simple pointer to a commit.
*   No extra metadata.
*   Quick and temporary.

2️⃣ **Annotated Tag (Recommended)**

```bash
git tag -a v1.0 -m "Version 1.0 release"
```
*   Stores **tagger name, email, date, and message**.
*   Stored as a full object in Git.
*   Used for **production releases**; most companies prefer this type.

---

## 🔹 Tag Management Commands

**Tag a Specific Commit:**

```bash
git tag -a v1.1 commit_id -m "Bug fix release"
```

**List Tags:**

```bash
git tag
```
**List with a pattern:**

```bash
git tag -l "v1.*"
```

**Show Tag Details:**

```bash
git show v1.0
```

**Push Tags to Remote:**

*   **Push single tag:**
```bash
git push origin v1.0
```
*   **Push all tags:**
```bash
git push --tags
```
⚠️ **Note:** Tags are **NOT** pushed automatically with a normal `push`.

**Delete Tag:**

*   **Delete locally:**
```bash
git tag -d v1.0
```
*   **Delete from remote:**
```bash
git push origin --delete v1.0
```
---

## 🔥 Tags vs Branches (Interview Favorite)

| Feature | Tag | Branch |
| :--- | :--- | :--- |
| **Moves automatically** | ❌ | ✅ |
| **Used for versioning** | ✅ | ❌ |
| **Editable** | ❌ | ✅ |
| **Permanent marker** | ✅ | ❌ |

---

## 🎯 Interview Questions & Answers

1️⃣ **What is a Git tag?**

**Answer:** A label used to mark a specific commit, usually for version releases.

2️⃣ **What are the types of tags?**

**Answer:** Lightweight and Annotated.

3️⃣ **Which tag type is recommended for production?**

**Answer:** **Annotated tag**.

4️⃣ **Do tags move when new commits are added?**

**Answer:** **No.** They remain fixed to the commit they were created on.

5️⃣ **Are tags pushed automatically?**

**Answer:** **No.** You must push them explicitly using `git push --tags`.

6️⃣ **How do you create a tag for a previous commit?**

```bash
git tag -a v1.0 commit_id -m "release"
```

7️⃣ **What is semantic versioning?**

**Example:** `v1.2.3`
*   **1** → Major
*   **2** → Minor
*   **3** → Patch
This is a very common industry practice.

---

## 🔥 Real Interview Scenario

**Q: You are releasing version 2.0 to production. What will you do?**

**Correct answer:**
```bash
git tag -a v2.0 -m "Production release"
git push origin v2.0
```
---

## 🧠 Memory Trick

*   **Branch** = Moving pointer.
*   **Tag** = Permanent label.
