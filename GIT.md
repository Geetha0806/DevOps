# Interview Quick Glance:

## 1. What is a version control system (VCS)?

A version control system is a tool that help **manage, track and control changes** that are made to the source code over time.

- Helps us identify **who, when and what changes were made**
- Lets us go back to the **previous versions**
- Helps us **collaborate on project without overwriting** the each others work.

## 2. What are the different types of VCS?

There are three types of VCS:

| Type | Full Form                          | Examples                                                               |
| ---- | ---------------------------------- | ---------------------------------------------------------------------- |
| LVCS | Localized Version Control System   | RCS (Revision Control System) ​                               |
| CVCS | Centralized Version Control System | Subversion (SVN), Concurrent Versions System (CVS)  |
| DVCS | Distributed Version Control System | Git, Mercurial                                    |

## 3. Explain LVCS in detail?

- A Local Version Control System (LVCS) is the simplest form of version control where all the **files, versions, and history** are stored on a single local machine.
- There are **no servers** involved, **no internet dependency**, and **no built-in collaboration support**.
- LVCS tracks file changes over time on the local system, allowing users to save different versions and restore older states when required.

### Recorded Data
A version typically records:
- The file state
- Timestamp
- Change history

### Examples
- RCS (Revision Control System)
- Git (when used without any remote repository)

### Workflow

```plaintext
File → Change → Snapshot/Version → Local History
```

### Advantages

- Tracks file changes
- Maintains version history
- Supports rollback to older versions
- Works completely offline
- Very fast
- No server required

### Disadvantages

- No collaboration support
- Single point of failure (hard disk crash can cause data loss)
- No central backup
- Manual file sharing required


## 4. Explain CVCS in detail?

- A Centralized Version Control System (CVCS) uses a single central server (repository) where all versions and history of the project are stored.
- Multiple developers collaborate by checking out files from the central repository, making changes locally, and committing those changes back to the server, which then becomes available to everyone.
- CVCS tracks changes per file and follows a file-based versioning model.

### Typical Workflow

```plaintext
Central Repository (Server)
        ↑        ↓
     commit   checkout/update
        ↑        ↓
    Developers (latest version file)
(Updated file)

CVCS Architecture:
------------------

          [ Central Server ]
                 |
   --------------------------------
   |              |               |
[ Dev A ]      [ Dev B ]       [ Dev C ]
(working)     (working)       (working)

```

- **Checkout / Update** – A developer retrieves the latest version of files from the central repository
- **Make Changes** – The developer modifies files locally
- **Commit** – Changes are sent back to the central server and shared with others

### Examples
- SVN (Subversion)
- CVS (Concurrent Versions System)
- Perforce

### Advantages

- Enables collaboration
- Easier access and permission management
- Clear project structure
- Strong central control
- Suitable for large enterprises

### Disadvantages

- Single point of failure (server downtime affects everyone)
- Limited offline work (most operations require server access)
- Slower operations due to network dependency
- Risky collaboration – conflicts can occur when multiple users modify the same file

## 5. Explain DVCS in detail?

- A Distributed Version Control System (DVCS) is a version control system where every developer has a complete copy of the repository, including full project history.
- Unlike centralized systems, DVCS does not depend on a single central server. Developers can commit changes locally, and those changes are not visible to others until they are pushed to a shared remote repository.

### Workflow

```plaintext
 -------------------------------------------
        Remote Repository (optional - GITHUB)
 -------------------------------------------

   PUSH        ↑         ↓    FETCH ------------------
                                                     |
 -------------------------------------------         |
       Local Repository (GIT)                        |   PULL
 -------------------------------------------         |
                                                     |        
  COMMIT       ↑         ↓    MERGE ------------------

 -------------------------------------------     
         lOCAL SYSTEMS
 -------------------------------------------
        |           |           |
     Dev A        Dev B       Dev C
 (Full Repo)   (Full Repo)  (Full Repo)

```

- Developers write code in their local systems.
- They commit changes to their local repository.
- Changes remain private until pushed.
- Developers push their commits to a remote repository.
- Other developers fetch the changes.
- They merge them into their local branches.
- `git pull` is a combination of fetch + merge.

### Examples

- Git
- Mercurial
- Bazaar
(GitHub is a hosting platform for Git repositories.)

### Advantages
- Full collaboration support
- Offline work capability
- No single point of failure
- Faster operations
- Cheap and powerful branching
- Better conflict handling
- Multiple remote repositories supported

### Disadvantages
- Slightly steeper learning curve
- Large repositories consume more local storage
- Access control can be complex since full history is cloned

## 6. Is Git centralized or distributed?

> Git is a distributed version control system. However, platforms like Github provides centralized hosting for collaboration.

## 7. Difference between LVCS and CVCS and DVCS.


| Feature                  | LVCS                          | CVCS                          | DVCS                          |
|--------------------------|-------------------------------|-------------------------------|-------------------------------|
| **Full Form**            | Local Version Control System | Centralized Version Control System | Distributed Version Control System |
| **Repository Location**  | Only on local machine        | Single central server        | Every developer has full repository |
| **Collaboration**        | ❌ No                        | ✅ Yes                       | ✅ Yes                       |
| **Internet Required**    | ❌ No                        | ✅ Mostly required           | ❌ Not required for most operations |
| **Full History Available Locally** | ✅ Yes              | ❌ No                        | ✅ Yes                       |
| **Single Point of Failure** | ❌ Yes (local crash)     | ❌ Yes (server crash)       | ✅ No                        |
| **Speed**                | Fast                         | Slower (network dependent)  | Very fast                    |
| **Branching**            | Limited                      | Difficult                    | Easy & cheap                 |
| **Backup**               | ❌ No                        | Partial (server)             | ✅ Multiple copies           |
| **Examples**             | RCS                          | SVN, CVS                     | Git, Mercurial               |

## 8. What is Git?

> Git is an open-source Distributed Version Control System (DVCS) created by Linus Torvalds in 2005.
> It is used to track changes in source code and enable collaboration between multiple teams such as development, testing, and operations.
> Git is installed locally on each developer’s machine. After installation, a local repository can be created using git init or cloned from an existing repository using git clone.
> Git allows developers to work offline because most operations such as commit, branch, merge, and log do not require internet access. Internet is only required when synchronizing with a remote repository.
> Git efficiently supports branching and merging, making parallel development easier and faster.

### Advantages

- Distributed architecture (DVCS)
- Works offline
- Very fast performance
- Powerful branching & merging
- Data integrity (SHA-1 hashing)
- Open source
- Lightweight & scalable

### Disadvantages

- Steep learning curve for beginners
- Complex commands (rebase, reset, cherry-pick)
- Not ideal for very large binary files
- No built-in GUI (CLI heavy)

## 9. Explain Git Architecture?

<img width="892" height="1023" alt="image" src="https://github.com/user-attachments/assets/d801e328-9ef9-4717-8563-d7590507dcdd" />


<img width="928" height="634" alt="image" src="https://github.com/user-attachments/assets/eedd667c-d8c8-40ef-88d1-241daafed389" />

Git works using three main areas:

### 1️⃣ Working Directory (Workspace)

- This is the actual project folder where files are created, edited, or deleted.
- Files are initially untracked. When added using `git add`, they become tracked and move to the staging area.

### 2️⃣ Staging Area (Index)

- This is Git's pre-commit area.
- Changes are temporarily stored here before being committed.
- It allows developers to decide which changes should be included in the next commit.

### 3️⃣ Local Repository (.git folder)

- This is where Git permanently stores commits.
- When `git commit` is executed, staged changes are saved inside the .git directory.
- The .git folder contains:
        - Commit history
        - Branch references
        - Logs
        - Configuration files
        - Object database
- The presence of the .git folder makes a directory a Git repository.

## 10. What is GitHub?

**GitHub is a web-based hosting service for Git repositories that enables collaboration, code review, and remote code management.**

**GitHub** is:
- Web-based hosting platform for Git repositories
- Used as a remote/global repository
- Requires internet
- Provides collaboration features on top of Git

### 🔹 Purpose
- Store code in the cloud
- Enable team collaboration
- Manage and review code changes

### 🔹 Key Features
- Remote repository hosting
- Pull Requests (code review before merge)
- Branch management
- Issue tracking (bug/task management)
- Access control (roles & permissions)
- GitHub Actions (CI/CD automation)

### 🔹 How It Works with Git
- Developer works locally using Git
- Commit changes to local repository
- Push to GitHub (remote repository)
- Others pull the latest changes

### 🔹 Public vs Private Repositories
- **Public** → Anyone can view
- **Private** → Restricted access

## 11. Difference between Git and Github?

| Feature           | Git                              | GitHub                              |
|-------------------|----------------------------------|-------------------------------------|
| **Type**          | Version Control Tool            | Web-based Hosting Platform         |
| **Purpose**       | Track changes in code           | Host and manage Git repositories   |
| **Installation**  | Installed locally on system     | No installation required (browser-based) |
| **Internet**      | Not required                    | Required                           |
| **Works On**      | Local machine                   | Cloud / Remote server              |
| **Collaboration** | Limited (manual setup needed)   | Built-in collaboration features    |
| **Branching & Merging** | Yes                   | Uses Git features                  |
| **Code Review**   | No built-in feature             | Pull Requests for review           |
| **CI/CD**         | Not available                   | GitHub Actions available           |
| **Example**       | `git add`, `git commit`         | Push to github.com                 |

## 12. 
