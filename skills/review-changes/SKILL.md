---
name: review-changes
description: Review unstaged git changes for bugs, logic errors, and security problems
disable-model-invocation: true
---

Look at the currently unstaged changes in git and review them strictly for:

1. Bugs and logic errors
2. Security vulnerabilities
3. Race conditions or concurrency issues
4. Incorrect error handling
5. Edge cases that could cause failures
6. Other similar problems or room for improvements

Use `git diff` to see the unstaged changes. If there are no unstaged changes, check for staged changes with `git diff --cached` instead.

Be specific — reference file names and line numbers. Only flag things that actually matter.
