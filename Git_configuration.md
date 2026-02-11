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
