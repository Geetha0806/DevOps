1️⃣ **What is Git configuration?**

**Answer:**

Git configuration is used to set user identity and preferences such as username, email, editor, and default behavior. These settings control how Git operates.

2️⃣ **Why do we configure user.name and user.email?**

**Answer:**

Git uses `user.name` and `user.email` to record the author information in commits. This helps identify who made changes.

3️⃣ **How do you configure username and email globally?**

**Answer:**

```bash
git config --global user.name "Geetha Bai"
git config --global user.email "geetha@example.com"
```


4️⃣ **How do you check Git configuration?**

**Answer:**

```bash
git config --list
```

To check a specific value:
```bash
git config user.name
```


5️⃣ **What are the levels of Git configuration?**

**Answer:**

*   **System level** → Applies to all users.
*   **Global level** → Applies to current user.
*   **Local level** → Applies to a specific repository.
  

6️⃣ **Which configuration has highest priority?**

**Answer:**

**Local > Global > System**. 
Local configuration overrides global and system.

7️⃣ **Where are Git configuration files stored?**

**Answer:**

*   **System** → `/etc/gitconfig`.
*   **Global** → `~/.gitconfig`.
*   **Local** → `.git/config`.

8️⃣ **How do you configure settings only for one repository?**

**Answer:**

Navigate inside the repository and run:

```bash
git config user.name "Project Name"
```

(This sets local configuration.)

9️⃣ **How do you see from which file a configuration is coming?**

**Answer:**

```bash
git config --list --show-origin
```

🔟 **How do you remove a configuration?**

**Answer:**

```bash
git config --unset user.name
```

1️⃣1️⃣ **How do you change the default Git editor?**

**Answer:**

```bash
git config --global core.editor "vim"
```

1️⃣2️⃣ **Can different repositories have different usernames?**

**Answer:**

Yes. You can set different `user.name` and `user.email` at the local repository level.

1️⃣3️⃣ **How do you correct the author of the last commit?**

**Answer:**

```bash
git commit --amend --reset-author
```
---

Git allows you to configure settings at three different levels of priority.

## 🔹 1️⃣ Global Configuration

If you want to configure Git globally for your specific user account across all projects:

```bash
git config --global key value
```

**Example:**
```bash
git config --global user.name "Your Name"
```

*   **Scope:** Applies to all repositories for your user.
*   **Storage Locations:**
    *   **Windows:** `C:\Users\<User>\.gitconfig`.
    *   **Linux/Mac:** `~/.gitconfig`.

---

## 🔹 2️⃣ System-Level Configuration

If you want to configure Git for the entire machine, affecting every user:

```bash
git config --system key value
```

*   **Scope:** Applies to all users on the machine.
*   **Requirement:** Requires administrator or root privileges.
*   **Storage Locations:**
    *   **Windows:** `C:\Program Files\Git\etc\gitconfig`.
    *   **Linux/Mac:** `/etc/gitconfig`.

---

## 🔹 3️⃣ Local Configuration (Repository-Level)

If you are inside a specific Git repository and want settings to apply only to that project:

```bash
git config key value
```

*   **Scope:** Current repository only.
*   **Storage Location:** Stored within the project in `.git/config`.

---

## 🔥 Important: Priority Order (Interview Question)

If the same setting (such as `user.name`) exists at all three levels, Git follows a specific hierarchy to determine which value to use:

**Local > Global > System**

Git will always use the **local** value first if it is defined. For example, if you have a work email set globally but a personal email set locally in a specific project, Git will use the local personal email for that repository.

---

## 🎯 Summary Table

| Level | Command | Scope |
| :--- | :--- | :--- |
| **Local** | `git config` (no flag) | Current repository only |
| **Global** | `git config --global` | Current user account |
| **System** | `git config --system` | Entire machine/all users |
