---
name: review-style
description: Review unstaged git changes for code style and architectural cleanliness
disable-model-invocation: true
---

Look at the currently unstaged changes in git from a purely code style and architectural perspective.

Use `git diff` to see the unstaged changes. If there are no unstaged changes, check for staged changes with `git diff --cached` instead.

Review the changes for:

1. Code style issues (per the project's conventions in CLAUDE.md and README.md)
2. Architectural cleanliness and proper separation of concerns
3. Naming conventions and readability
4. Code structure and organization
5. Maintainability concerns

Do NOT think about logical bugs, security problems, or correctness. Focus only on ensuring we have a clean, well-structured, maintainable code base. Be specific — reference file names and line numbers. Only flag things that actually matter.
