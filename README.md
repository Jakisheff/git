# Git Exercises Project

Welcome to the Git Exercises project! This directory contains all the work done to master Git version control, from basic commits to advanced branching and remote repository management.

## 📂 Project Structure

This directory contains the following repositories and files:

- **`hello/`**: The main repository where most exercises were performed.
  - Contains the commit history for Setup, Commits, History, Branching, Merging, and Rebase tasks.
- **`cloned_hello/`**: A clone of the `hello` repository used to demonstrate local/remote interactions.
- **`hello.git/`**: A bare repository serving as the shared remote.

## 📄 Key Solution Files

These are the files you should present to the auditor:

1.  **[documentation.md](documentation.md)**
    - **Purpose**: The main solution file.
    - **Content**: A comprehensive log of every command executed for each task, serving as the required report/documentation.

2.  **[audit_answers.md](audit_answers.md)**
    - **Purpose**: Preparation for the oral audit.
    - **Content**: Detailed answers to conceptual questions (e.g., "Merging vs. Rebasing", ".git internals").

3.  **Commit History**
    - To view the evolution of the work, first restore the `.git` directory inside `hello`:
      ```bash
      mv hello/.git_keep hello/.git
      cd hello
      git log --oneline --graph --all
      ```
    - Similarly for `cloned_hello` (`mv cloned_hello/.git_keep cloned_hello/.git`) and `hello.git` bare repo (`mv hello.git_keep hello.git`).

## 🚀 How to Verify

You can verify the work by traversing the history of the `hello` repository or by checking the synchronization between `hello` and `cloned_hello`.

> **Note**: For submission purposes, nested `.git` directories have been renamed to `.git_keep` to allow including them in the main repository. Please rename them back to `.git` to use git commands inside the subdirectories.

---
*Generated for the Git Exercise Project Audit*
