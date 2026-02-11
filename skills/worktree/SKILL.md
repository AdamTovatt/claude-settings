---
name: worktree
description: Create or update a git worktree for a branch
disable-model-invocation: true
---

The user wants to work on a branch in a separate worktree. The branch name is provided as the argument: `$ARGUMENTS`.

If no branch name argument was provided, ask the user which branch they want.

Follow these steps:

1. **Fetch latest from remote** by running `git fetch origin`.

2. **Determine the worktree path**: `../ordo-<branch-name>` (relative to the repo root). For example, branch `azure-session-lifetime-management` becomes `../ordo-azure-session-lifetime-management`.

3. **Check if the worktree already exists** by running `git worktree list` and checking if the path is already listed.

4. **If the worktree does NOT exist:**
   - Run `git worktree add ../ordo-<branch-name> <branch-name>` to create it.
   - If that fails because the branch doesn't exist locally, try `git worktree add -b <branch-name> ../ordo-<branch-name> origin/<branch-name>` to create a local branch tracking the remote.
   - If that also fails (branch doesn't exist on remote either), create a new branch from master: `git worktree add -b <branch-name> ../ordo-<branch-name> origin/master`.
   - Tell the user what happened (checked out existing branch, or created new branch from master).

5. **If the worktree ALREADY exists:**
   - Run `git -C ../ordo-<branch-name> pull` to get the latest changes.
   - Tell the user the worktree was already set up and latest changes have been pulled.

6. **Tell the user how to start working there.** Print a message like:

   ```
   Worktree ready! To start Claude in the worktree, run:
   cd ../ordo-<branch-name> && claude
   ```
