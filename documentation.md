# Git Exercises Documentation

This document records the commands and process followed for the Git exercises.

## 1. Setting Up Git
- Initialized work directory: `mkdir hello && cd hello`
- Initialized repository: `git init`
- Renamed default branch to `main`: `git branch -m master main`

## 2. Git Commits
- Created `hello.sh` with "Hello, World": `echo 'echo "Hello, World"' > hello.sh`
- Committed: `git add hello.sh && git commit -m "Initial commit"`
- Updated to accept argument: `git commit -m "Updated hello.sh to accept a command line argument"`
- Added comments and default variable in separate commits:
  - `git commit -m "Added a comment"`
  - `git commit -m "Updated hello.sh with default name variable"`

## 3. History
- Checked history: `git log`
- One-line history: `git log --oneline`
- Last 2 entries: `git log --oneline -2`
- Last 5 minutes: `git log --oneline --since="5 minutes ago"`
- Personalized format: `git log --pretty=format:"* %h %ad | %s%d [%an]" --date=short`

## 4. Check it out (Time Travel)
- Restored first snapshot: `git checkout <hash>`
- Restored second snapshot: `git checkout <hash>`
- Returned to latest: `git checkout main`

## 5. TAG me
- Tagged current version: `git tag v1`
- Tagged previous version: `git tag v1-beta v1^`
- Navigated tags: `git checkout v1-beta`, `git checkout v1`
- Listed tags: `git tag`

## 6. Changed your mind? (Reverts)
- Reverted unstaged changes: `git checkout -- hello.sh`
- Unstaged staged changes: `git reset HEAD hello.sh` then `git checkout -- hello.sh`
- Reverted committed changes: `git revert HEAD`
- Tagged `oops`, reset to `v1`: `git tag oops`, `git reset --hard v1`
- Cleaned deleted commits: `git tag -d oops`, `git reflog expire --expire=now --all`, `git gc --prune=now`
- Added author and amended commit: `git commit --amend`

## 7. Move it & Blobs
- Moved `hello.sh` to `lib/`: `mkdir lib && git mv hello.sh lib/hello.sh`
- Created `Makefile`: `git add Makefile && git commit`
- Explored `.git` objects: `git ls-tree`, `git cat-file -p`

## 8. Branching
- Created branch: `git checkout -b greet`
- Added `lib/greeter.sh` and updated `lib/hello.sh`, `Makefile`
- On `main`, added `README.md`
- Viewed diverging history: `git log --all --graph --oneline`

## 9. Conflicts, Merging and Rebasing
- Merged `main` into `greet`: `git checkout greet && git merge main`
- Updated `main` with interactive prompt (conflict source)
- Attempted merge `main` into `greet` -> Conflict
- Resolved conflict by accepting `main` (ours): `git checkout --ours lib/hello.sh && git add lib/hello.sh && git commit`
- Reset and rebased `greet` onto `main`:
  - `git reset --hard <pre-merge-commit>`
  - `git rebase main`
  - Resolved rebase conflict (accepted `main`): `git checkout --ours lib/hello.sh`, `git rebase --continue`
- Merged `greet` into `main` (Fast-forward): `git checkout main && git merge greet`

## 10. Local and Remote Repositories
- Cloned repository: `git clone hello cloned_hello`
- Verified remotes: `git remote -v`
- Updated `hello`'s README
- Fetched and merged in `cloned_hello`: `git fetch`, `git merge origin/main`
- Tracked remote branch: `git checkout greet`
- Pushed (no-op as up to date): `git push origin main greet`

## 11. Bare Repositories
- Created bare repo: `git clone --bare hello hello.git`
- Added `shared` remote to `hello`: `git remote add shared ../hello.git`
- Updated README in `hello`, pushed to `shared`: `git push shared main`
- Added `shared` remote to `cloned_hello`, pulled changes: `git remote add shared ../hello.git && git pull shared main`

## Conclusion
All exercises completed successfully, demonstrating proficiency in Git workflow, branching, conflict resolution, rebase, and remote repository management.
