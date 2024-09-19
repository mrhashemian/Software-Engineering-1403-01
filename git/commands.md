# Git basic commands

1. [Init](#1-init): Initialize a new Git repository in the current directory.
2. [Clone](#2-clone): Create a copy of a remote repository on your local machine.
3. [Add](#3-add): Stage changes in specified file(s) for the next commit.
4. [Commit](#4-commit): Record changes to the repository with a descriptive message.
5. [Status](#5-status): Display the state of the working directory and staging area.
6. [Push](#6-push): Upload your local changes to the remote repository.
7. [Pull](#7-pull): Fetch and merge changes from the remote repository to your current branch.
8. [Branch](#8-branch): List all branches in the repository or create a new branch.
9. [Checkout](#9-checkout): Switch to a specified branch or restore files.
10. [Merge](#10-merge): Combines changes from the specified branch into your current branch.
11. [Stash](#11-stash): Temporarily saves changes in the working directory that are not ready to be committed.
12. [Log](#12-log): Displays a chronological list of commits in the repository.
13. [Diff](#13-diff): Show differences between the working directory and the index or between commits.
14. [Restore](#14-restore): Discard changes in the working directory and restore files to the last committed state.

---

## 1. Init

**Usage:** `git init`

**Description:** Initializes a new Git repository in the current directory. This creates a `.git` subdirectory.

**Example:**

  ```bash
  git init
  ```

---

## 2. Clone

**Usage:** `git clone <repository_url>`

**Description:** Creates a local copy of a remote repository.

**Example:**

```bash
git clone https://github.com/user/repo.git
```

---

## 3. Add

**Usage:** `git add <file>`

**Description:** Stages changes in the specified file(s) for the next commit.

**Examples:**

- To stage a specific file:

```bash
git add filename.txt
```

- To stage all changes:

```bash
git add .
```

---

## 4. Commit

**Usage:** `git commit -m "commit message"`

**Description:** Records changes to the repository. The message should describe what changes were made.

**Example:**

```bash
git commit -m "Fix bug in feature"
```

**Options:**

- **--amend:** Modifies the most recent commit. Use this to add changes to the last commit instead of creating a new
  one.

  **Example:**
  ```bash
  git commit --amend -m "Updated commit message"
  ```

---

## 5. Status

**Usage:** `git status`

**Description:** Displays the state of the working directory and staging area.

**Example:**

```bash
git status
```

---

## 6. Push

**Usage:** `git push [origin] [branch]`

**Description:** Uploads your local commits to the remote repository.

**Example:**

```bash
git push origin main
```

---

## 7. Pull

**Usage:** `git pull [origin] [branch]`

**Description:** Fetches changes from the remote repository and merges them into your current branch.

**Example:**

```bash
git pull origin main
```

---

## 8. Branch

**Usage:** `git branch [branch_name]`

**Description:** Lists all branches or creates a new branch if a name is provided.

**Example (list branches):**

```bash
git branch
```

**Example (create branch):**

```bash
git branch new-feature
```

---

## 9. Checkout

**Usage:** `git checkout <branch_name>`

**Description:** Switches to the specified branch or restores files in the working directory.

**Example:**

```bash
git checkout feature-branch
```

**Options:**

- **-b:** Creates new branch with specified name if it doesn't exist then checkout to it.

  **Example:**
  ```bash
  git checkout -b feature-branch
  ```

---

## 10. Merge

**Usage:** `git merge <branch_name>`

**Description:** Combines changes from the specified branch into your current branch.

### Basic Usage

1. **Ensure you’re on the target branch** (the branch you want to merge changes into).
   ```bash
   git checkout main
   ```

2. **Merge the specified branch**.
   ```bash
   git merge feature-branch
   ```

### Example Workflow

1. **Start on your main branch:**
   ```bash
   git checkout main
   ```

2. **Make sure your main branch is up to date:**
   ```bash
   git pull origin main
   ```

3. **Merge a feature branch:**
   ```bash
   git merge feature-branch
   ```

### Handling Merge Conflicts

When merging, if there are changes in both branches that conflict, Git will notify you of a merge conflict. You’ll need
to resolve these conflicts manually.

**Steps to Resolve Conflicts:**

1. **Check the status** to see which files have conflicts:
   ```bash
   git status
   ```

2. **Open the conflicted files** in your text editor and look for conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`).

3. **Resolve the conflicts** by choosing which changes to keep, then remove the conflict markers.

4. **Stage the resolved files:**
   ```bash
   git add resolved-file.txt
   ```

5. **Complete the merge** by committing:
   ```bash
   git commit -m "Resolved merge conflicts and merged feature-branch into main"
   ```

---

## 11. Stash

**Usage:** `git stash`

**Description:** Temporarily saves changes in the working directory that are not ready to be committed.

**Example (stash changes):**

```bash
git stash
```

**Options:**

- **apply:** Applies the most recent stash.

  **Example:**
  ```bash
  git stash apply
  ```

- **pop:** Applies the most recent stash and removes it from the stash list.

  **Example:**
  ```bash
  git stash pop
  ```

- **drop:** Deletes a specific stash from the stash list.

  **Example:**
  ```bash
  git stash drop stash@{0}
  ```

---

## 12. Log

**Usage:** `git log`

**Description:** Displays a chronological list of commits in the repository.

**Example:**

```bash
git log
```

---

## 13. Diff

**Usage:** `git diff`

**Description:** Shows the differences between the working directory and the index (staged changes), or between
commits, branches, etc.

**Examples:**

- To see unstaged changes:

```bash
git diff
```

- To see staged changes:

```bash
git diff --cached
```

- To compare two branches:

```bash
git diff branch1 branch2
```

---

## 14. Restore

**Usage:** `git restore <file>`

**Description:** Discards changes in the working directory and restores the file to the last committed state.

**Example:**

  ```bash
  git restore filename.txt
  ```

**Note:** You can also use `git restore --staged <file>` to un-stage changes.
