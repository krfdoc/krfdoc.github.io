---
title: Git Commands
date: 2022-11-10 09:00:00 -0500
categories: [linux,git]
tags: [linux,git]
---

## Some Git commands

### Scenario: 
You just ran git push, sending your changes to GitHub, now you realize there’s a problem with one of those commits. You’d like to undo that commit.

```terminal
git revert <SHA>
```

* SHA is the same as commit_id I believe

What’s happening: git revert will create a new commit that’s the opposite (or inverse) of the given SHA. If the old commit is “matter”, the new commit is “anti-matter”—anything removed in the old commit will be added in the new commit and anything added in the old commit will be removed in the new commit.

This is Git’s safest, most basic “undo” scenario, because it doesn’t alter history—so you can now git push the new “inverse” commit to undo your mistaken commit.


### Scenario:
You just typo’d the last commit message, you did git commit -m "Fxies bug #42" but before git push you realized that really should say “Fixes bug #42”.

```terminal
git commit --amend
```
or
```terminal
git commit --amend -m "Fixes bug #42"
```

What’s happening: git commit --amend will update and replace the most recent commit with a new commit that combines any staged changes with the contents of the previous commit. With nothing currently staged, this just rewrites the previous commit message.