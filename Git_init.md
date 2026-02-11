1️⃣ **What is git init?**

**Answer:**

`git init` is used to initialize a new Git repository. It creates a hidden **.git folder** that stores version history, configuration, and metadata.

2️⃣ **What happens internally when you run git init?**

**Answer:**

*   A **.git directory** is created.
*   The **default branch** is initialized.
*   Git starts **tracking changes** in that directory.

3️⃣ **Does git init track files automatically?**

**Answer:**

No. It only initializes the repository. Files must be added using `git add` to start tracking.

4️⃣ **What is stored inside the .git folder?**

**Answer:**

The `.git` folder stores the following metadata and history:
*   Commit history
*   Branch information
*   Object database
*   Configuration
*   HEAD pointer

5️⃣ **What happens if you run git init inside an existing repository?**

**Answer:**

It **reinitializes** the repository but does not delete existing history.

6️⃣ **What is the difference between git init and git clone?**

**Answer:**

| Feature | git init | git clone |
| :--- | :--- | :--- |
| **Purpose** | Creates a new empty repository | Copies an existing repository |
| **History** | No history initially | Includes full history |
| **Use Case** | Used to start a project | Used to download a project |

7️⃣ **What is a bare repository?**

**Answer:**

A bare repository is typically used as a remote/server repository and is created using:
```bash
git init --bare
```
It **does not contain a working directory**.

8️⃣ **What is the difference between normal and bare repository?**

**Answer:**

*   **Normal repo** → Has a working directory.
*   **Bare repo** → No working directory, only Git data.

9️⃣ **How do you set the default branch while initializing?**

**Answer:**

```bash
git init -b main
```

🔟 **Can you convert an existing project into a Git repository?**

**Answer:**

Yes. Navigate into the project directory and run:
```bash
git init
```

1️⃣1️⃣ **How do you initialize a git repository for a specific project?**

**Answer:**

To initialize a repository with a specific name, use:
```bash
git init project-name
```
