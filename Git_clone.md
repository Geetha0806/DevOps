## 🔹 What is git clone?

**git clone** is used to copy an existing remote repository to your local system.

**It performs the following actions:**

*   Downloads the full project.
*   Copies the complete commit history.
*   Creates a working directory.
*   Automatically sets the remote as **origin**.

### 🔹 Basic Syntax

```bash
git clone <URL>
```

**Example:**

```bash
git clone https://github.com/user/project.git
```

### 🔹 What Happens Internally?

When you run `git clone`:
1.  It creates a new folder (usually the project name).
2.  It copies the entire repository, including the hidden **.git folder**.
3.  It sets the remote name as **origin**.
4.  It checks out the default branch, which is usually **main**.

---

## 🔹 Important Variants of git clone

1️⃣ **Clone into Specific Folder**

```bash
git clone <URL> folder-name
```
**Example:**

```bash
git clone https://github.com/user/project.git myproject
```


2️⃣ **Clone Specific Branch**

```bash
git clone -b branch-name <URL>
```
**Example:**

```bash
git clone -b develop https://github.com/user/project.git
```


3️⃣ **Shallow Clone (Very Important)**

```bash
git clone --depth 1 <URL>
```
This clones only the **latest commit** without the full history. It is used for faster downloads and in **CI/CD pipelines**.

4️⃣ **Clone Using SSH**

```bash
git clone git@github.com:user/project.git
```
Used when **SSH keys** are configured on your system.

5️⃣ **Mirror Clone (Advanced)**

```bash
git clone --mirror <URL>
```
Creates a bare mirror repository that includes all references.

6️⃣ **Bare Clone**

```bash
git clone --bare <URL>
```
Creates a repository **without a working directory**. This is typically used for remote servers.

---

## 🔹 Scenario-Based Interview Questions

1️⃣ **What is the difference between git clone and git init?**

| Feature | git clone | git init |
| :--- | :--- | :--- |
| **Action** | Copies an existing repository | Creates a new empty repository |
| **History** | Includes full history | No history initially |
| **Remote** | Automatically sets remote | Must manually add remote |

2️⃣ **What remote name is automatically set after cloning?**

**Answer:** origin.

3️⃣ **Does git clone copy full commit history?**

**Answer:** Yes, unless the `--depth` flag is used.

4️⃣ **What is a shallow clone?**

**Answer:** A clone with limited history created using `git clone --depth 1`.

5️⃣ **What is the difference between HTTPS and SSH cloning?**

| Feature | HTTPS | SSH |
| :--- | :--- | :--- |
| **Authentication** | Requires username/password or token | Uses SSH key |
| **Setup** | Easier setup | More secure for frequent use |

6️⃣ **What is the difference between a normal clone and a bare clone?**

| Feature | Normal Clone | Bare Clone |
| :--- | :--- | :--- |
| **Working Directory** | Has working directory | No working directory |
| **Use Case** | Used for development | Used as remote/server |

---

## 🔹 Deep Understanding Questions

7️⃣ **What protocols does git clone use?**

**Answer:** It can use **HTTPS**, **SSH**, or the **Git protocol**.

8️⃣ **Where is remote configuration stored after cloning?**

**Answer:** In the **.git/config** file.
