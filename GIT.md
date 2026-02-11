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
