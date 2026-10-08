---
name: pr-description
description: Writes pull request descriptions. Use when creating a PR, writing a PR,
  or when the user asks to summarize changes for a pull request.
---

When writing a PR description:

1. Run `git diff main...HEAD` to see all changes on this branch
2. Write a description following this format:

## What
One sentence explaining what this PR does.

## Why
Brief context on why this change is needed

## Changes
- Bullet points of specific changes made
- Group related changes together
- Mention any files deleted or renamed

The description is complete when all of these are true:

- It has the three sections What, Why, and Changes, in that order.
- What is exactly one sentence.
- Every file in the `git diff main...HEAD` output is covered by a bullet under Changes.
- Deleted and renamed files are named.
- No placeholder text such as "TODO" or "describe here" remains.
