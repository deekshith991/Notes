
---
title: Git - Version Control System
aliases:
  - Git Notes
  - Git Basics
tags:
  - git
  - version-control
  - development
  - swayam course
created: 2026-05-11
updated: 2026-05-11
author: Deekshith Vaggu
status: completed
---

# GIT - Version Control System

- create a git repo
```git
git init .
```

- setup user config
```git
git config --global user.email "email_address"
git config --global user.name "user_name"
git config --global core.editor vim
```

- --global means this config will be used for all repos on this machine.

- track a file / stage a file
```git
git add file_name
```

- Untrack a file / de-stage a file
```git
git rm --cached file_name
git restore --staged file_name
```

- check status of a file
```git
git status

output:

On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	ESim.md
	git.md

nothing added to commit but untracked files present (use "git add" to track)
```

- commit the file changes
```git
git commit
```
then enter the commit message in the editor that u have configured.
the commit is added to repo with a SHA1 hash 
the string after commit is the SHA1 hash string

use -a for add instead of add command -m for message.

- show git logs
```git
git log

output:

commit c379cd936a379677e8f1d7ea47ca9b6d530d7e37
Author: Deekshith vaggu <vaggudeekshith@gmail.com>
Date:   Sat May 9 22:27:27 2026 +0530

    Video 13 & 14

commit 49783a5e63001658ac8f7d42372047a2848bd7c0
Author: Deekshith vaggu <vaggudeekshith@gmail.com>
Date:   Sat May 9 10:33:43 2026 +0530

    Video 11 & 12

```

- check the changes made in the repo
```git
git diff
```

- Discard the changes that are not committed.
```git
git restore file_name
git checkout .
```
> [!WARNING]
> the checkout is the simple method not recommended. this can on;y be used if we don't want any changes in all the files. 

> [!WARNING]
> Using this destroys all the commits. Pls Avoud this at all cost
- we want to discard all the commits from the given commit hash
```git
git reset hard --hard commit_hash
```



