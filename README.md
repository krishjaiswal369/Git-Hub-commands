# Git Command Master Reference

A comprehensive, clean, and production-ready reference guide comprising essential Git commands, core descriptions, and practical, real-world development examples. Cleaned, corrected, and structured from the master document.

---

## 📋 Table of Contents
1. [1. Setup & Initialization](#1-setup--initialization)
2. [2. Basic Snapshotting & Staging](#2-basic-snapshotting--staging)
3. [3. Branching & Merging](#3-branching--merging)
4. [4. Inspecting History & Comparison](#4-inspecting-history--comparison)
5. [5. Sharing & Syncing Repositories (Remotes)](#5-sharing--syncing-repositories-(remotes))
6. [6. Stashing Temporary Changes](#6-stashing-temporary-changes)
7. [7. Advanced Undo, Rescue & Patching](#7-advanced-undo,-rescue--patching)
8. [8. Maintenance, Administration & Submodules](#8-maintenance,-administration--submodules)

---

## 1. Setup & Initialization

| Command | Description | Practical Example |
| :--- | :--- | :--- |
| ` git init ` | Create a new local Git repository. | ` git init my-repo ` |
| ` git clone ` | Clone a repository into a new directory. | ` git clone https://github.com/user/repo.git ` |
| ` git config ` | Get and set repository or global options. | ` git config --global user.email "you@example.com" ` |
| ` git config --list ` | List all active Git configuration settings from system, global, and local layers. | ` git config --list ` |

## 2. Basic Snapshotting & Staging

| Command | Description | Practical Example |
| :--- | :--- | :--- |
| ` git add ` | Stage changes for the next commit. | ` git add file.txt ` |
| ` git commit ` | Record staged changes in the repository. | ` git commit -m "Add feature" ` |
| ` git commit --amend ` | Modify the most recent commit by combining staged changes or altering the message. | ` git commit --amend -m "Updated fix" ` |
| ` git status ` | Show the working tree status. | ` git status ` |
| ` git rm ` | Remove files from working tree and index. | ` git rm obsolete.txt ` |
| ` git mv ` | Move or rename a file, directory, or symlink. | ` git mv oldname newname ` |
| ` git restore ` | Restore working tree files or discard local changes (modern form). | ` git restore src/app.js ` |
| ` git clean ` | Remove untracked files from the working tree. | ` git clean -fd ` |

## 3. Branching & Merging

| Command | Description | Practical Example |
| :--- | :--- | :--- |
| ` git branch ` | List, create, or delete branches. | ` git branch feature/login ` |
| ` git branch -d ` | Delete a local branch that has been safely merged downstream. | ` git branch -d feature/old-login ` |
| ` git branch -m ` | Rename the current active branch or a specified branch. | ` git branch -m feature/new-login ` |
| ` git checkout ` | Switch branches or restore files (older legacy form). | ` git checkout feature/login ` |
| ` git checkout -b ` | Create a new branch and immediately switch to it (legacy shorthand). | ` git checkout -b feature/payment ` |
| ` git switch ` | Switch branches (safer, dedicated modern command). | ` git switch -c feature/login ` |
| ` git merge ` | Join two or more development histories together. | ` git merge main ` |
| ` git merge-abort ` | Stop the merge process and reconstruct the pre-merge state if conflicts occur. | ` git merge-abort ` |
| ` git rebase ` | Reapply commits on top of another base tip. | ` git rebase main ` |
| ` git rebase -i ` | Interactive rebase to edit, squash, or reorder commits. | ` git rebase -i HEAD~5 ` |
| ` git worktree ` | Manage multiple working trees attached to the same repository. | ` git worktree add ../repo-worktree feature/login ` |

## 4. Inspecting History & Comparison

| Command | Description | Practical Example |
| :--- | :--- | :--- |
| ` git status ` | Show the working tree status. | ` git status ` |
| ` git log ` | Show commit history. | ` git log --oneline --graph ` |
| ` git shortlog ` | Summarize git log output by author. | ` git shortlog -sne ` |
| ` git reflog ` | Show a log of where HEAD and branches have been over time. | ` git reflog ` |
| ` git diff ` | Show changes between commits, branches, or working tree. | ` git diff HEAD~1 HEAD ` |
| ` git diff --staged ` | Show changes between files staged for the next commit and the last commit. | ` git diff --staged ` |
| ` git show ` | Show various types of objects (commits, tags, files). | ` git show HEAD~1 ` |
| ` git blame ` | Show what revision and author last modified each line of a file. | ` git blame src/app.js ` |
| ` git grep ` | Search for regular expression patterns in the repository content. | ` git grep "TODO" ` |
| ` git describe ` | Describe a commit using the nearest readable tag. | ` git describe --tags --always ` |

## 5. Sharing & Syncing Repositories (Remotes)

| Command | Description | Practical Example |
| :--- | :--- | :--- |
| ` git remote ` | Manage the set of tracked remote repositories. | ` git remote -v ` |
| ` git remote add ` | Associate a local repository with a new remote URL connection. | ` git remote add origin https://github.com/user/repo.git ` |
| ` git remote set-url ` | Change the target URL of an existing remote repository connection. | ` git remote set-url origin https://github.com/user/new.git ` |
| ` git fetch ` | Download objects and refs from another repository. | ` git fetch origin ` |
| ` git fetch --all ` | Fetch updates from all tracked remotes simultaneously. | ` git fetch --all --prune ` |
| ` git pull ` | Fetch from and integrate with another repository or a local branch. | ` git pull origin main ` |
| ` git push ` | Update remote refs along with associated objects. | ` git push origin feature/login ` |
| ` git push-tags ` | Push all local release tags up to the remote server repository. | ` git push origin --tags ` |
| ` git push origin -d ` | Delete a specified branch or tag from the remote repository. | ` git push origin --delete feature/login ` |

## 6. Stashing Temporary Changes

| Command | Description | Practical Example |
| :--- | :--- | :--- |
| ` git stash ` | Stash local modifications away to quickly clean the working directory. | ` git stash push -m "WIP: refactor" ` |
| ` git stash pop ` | Apply the latest stashed state and remove it from the stash list. | ` git stash pop ` |
| ` git stash apply ` | Apply a specific stash state without removing it from the list. | ` git stash apply stash@{1} ` |
| ` git stash list ` | List all currently saved stashed changesets. | ` git stash list ` |
| ` git stash drop ` | Permanently discard a specific stashed changeset from your list. | ` git stash drop stash@{0} ` |
| ` git stash clear ` | Completely wipe out and remove all stashed records. | ` git stash clear ` |

## 7. Advanced Undo, Rescue & Patching

| Command | Description | Practical Example |
| :--- | :--- | :--- |
| ` git cherry-pick ` | Apply changes introduced by existing individual historical commits. | ` git cherry-pick a1b2c3d ` |
| ` git cherry ` | List commits that have not yet been merged upstream. | ` git cherry -v origin/main ` |
| ` git revert ` | Create a new safe commit that completely undoes mutations from a prior commit. | ` git revert a1b2c3d ` |
| ` git reset ` | Reset current HEAD pointer to a specified state (soft/mixed). | ` git reset --soft HEAD~1 ` |
| ` git reset --hard ` | Reset current branch HEAD, wiping out all uncommitted and tracked modifications. | ` git reset --hard HEAD~1 ` |
| ` git bisect ` | Use binary search strategy to locate the commit that introduced a regression/bug. | ` git bisect start; git bisect bad; git bisect good <commit> ` |
| ` git format-patch ` | Prepare electronic emailable patches directly out of historical commits. | ` git format-patch -3 ` |
| ` git am ` | Apply individual patches from structured mailbox (mbox) formatted files. | ` git am 0001-fix-bug.patch ` |
| ` git apply ` | Apply a raw unified diff patch file onto files or index directly. | ` git apply fix.patch ` |

## 8. Maintenance, Administration & Submodules

| Command | Description | Practical Example |
| :--- | :--- | :--- |
| ` git tag ` | Create, list, or delete release tags mapping specific history checkpoints. | ` git tag -a v1.0 -m "Release 1.0" ` |
| ` git submodule ` | Manage complex nested embedded repositories within a parent repository. | ` git submodule add https://github.com/lib/lib.git deps/lib ` |
| ` git submodule update ` | Initialize, fetch, and checkout all configured submodules recursively. | ` git submodule update --init --recursive ` |
| ` git archive ` | Create a clean zip or tar archive of elements originating from a named tree. | ` git archive --format tar --output project.tar HEAD ` |
| ` git fsck ` | Verify object database health, matching connectivity and validity. | ` git fsck --full ` |
| ` git gc ` | Cleanup unnecessary garbage tracking files and optimize database performance. | ` git gc --prune=now ` |
| ` git bundle ` | Pack or unpack binary multi-object offline transport container bundles. | ` git bundle create repo.bundle --all ` |
| ` git notes ` | Add or inspect textual meta-notes attached to active objects safely. | ` git notes add -m "Reviewed" ` |
| ` git rerere ` | Reuse recorded automated resolutions of identical long-term merge conflicts. | ` git rerere enabled ` |

---

## 💡 Pro-Tips for Reference
* **Modern vs Legacy Forms:** Prefer modern dedicated options like `git switch` over the legacy usage of `git checkout` for switching branches, as it prevents accidental loss of untracked file modifications.
* **Safer Undos:** When rolling back local changes, `git revert` is always preferred for shared, public remote branches because it generates a safe history-preserving trailing patch rather than stripping tree branches via `git reset`.
* **Submodule Tracking:** Always append `--recursive` to updates if working on legacy, multi-layered architectures containing deep nested modules.
