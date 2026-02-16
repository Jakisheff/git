# Audit Preparation & Answers

This document provides answers to the conceptual questions likely to be asked during your audit, and confirms the completion of all practical tasks.

## Conceptual Questions & Answers

### 1. The .git Directory
The auditor will ask you to explain the purpose of each subdirectory in `.git/`.

- **objects/**: The database of your repository. It stores all content (file contents as blobs, commit objects, tree objects, and tags). When you commit, git stores snapshots here.
- **config**: The configuration file specific to this repository. It stores settings like remote URLs (`origin`), branch tracking information, and user details if set locally.
- **refs/**: Stores references (pointers) to commit objects.
  - `refs/heads/`: Local branches (e.g., `main`, `greet`).
  - `refs/tags/`: Tags (e.g., `v1`).
  - `refs/remotes/`: Tracking branches from remote repositories (e.g., `origin/main`).
- **HEAD**: A special reference that points to the current branch or commit you are working on. It tells git what the parent of the next commit will be.

### 2. Merging vs. Rebasing
**Question**: "Explain the difference between merging and rebasing and if you understand Fast-Forwarding."

- **Merging**: Combines two branches together. It creates a new "merge commit" that has two parents (the tips of both branches). It preserves the exact history of when and how changes happened.
- **Rebasing**: Takes a series of commits from one branch and reapplies them on top of another base commit. It rewrites history to create a linear progression, as if you had started your work from the latest version of the main branch.
- **Fast-Forwarding**: This happens when you merge a branch that is directly ahead of your current branch. Git simply moves the pointer forward to the new commit without creating a merge commit, because there is no divergent history to reconcile.

### 3. Fetch + Merge Equivalent
**Question**: "What is the single git command equivalent to what you did before to bring changes from remote to local main branch?"
**Answer**: `git pull` (which combines `git fetch` and `git merge`).

### 4. Bare Repositories
**Question**: "What is a bare repository and why is it needed?"
**Answer**: A bare repository (`git clone --bare`) contains only the version control information (the contents of the `.git` directory) and **no working directory**. You cannot edit files directly inside it.

**Why needed?**: It serves as a central hub for sharing code. Since no one works directly inside it, there are no conflicts when multiple users push to it. Pushing to a non-bare repository is generally blocked if the branch is checked out, to prevent overwriting someone's work in progress.

---

## Practical Checklist Confirmation

The following tasks have been completed and are documented in [`documentation.md`](documentation.md):

- [x] **Setup**: Git installed & configured.
- [x] **Commits**: `hello` repo created, `hello.sh` committed with message, argument, & comments.
- [x] **History**: `git log` used with various formats (oneline, -2, personalized).
- [x] **Checkout**: Restored snapshots, returned to `main`.
- [x] **Tags**: `v1` and `v1-beta` created and navigated.
- [x] **Reverts**: Unstaged, staged, and committed changes reverted. History cleaned.
- [x] **Move**: `hello.sh` moved to `lib/`, `Makefile` created.
- [x] **Blobs/Trees**: Explored `.git` objects.
- [x] **Branching**: `greet` branch created, new files added, diff compared.
- [x] **Merging/Rebasing**: `main` merged into `greet`, conflict created & resolved, then rebased.
- [x] **Local & Remote**: Cloned to `cloned_hello`, fetched, merged, pushed.
- [x] **Bare Repo**: created `hello.git`, used as shared remote for push/pull.
