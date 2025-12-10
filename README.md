# Git-Practice — A compact practice book for Git

## Overview

- This repository is a hands-on practice book for Git. It explains the essential
	commands, shows concise examples, and includes practical exercises you can run
	locally.

Use this guide interactively: try each command in a disposable folder or a test
repo so you can experiment safely.

---

## Quick start (setup)

1. Set your identity (done once):

```bash
git config --global user.name "Your Name"
git config --global user.email you@example.com
```

2. Create a new repository in the current folder:

```bash
git init
```

3. Or clone an existing remote repository:

```bash
git clone https://github.com/user/repo.git
```

---

## Core workflow (the essentials)

1) Inspect the working directory

```bash
git status        # shows tracked/untracked changes and branch info
git diff          # shows unstaged changes
git diff --staged # shows staged changes (what will be committed)
```

2) Stage and commit changes

```bash
git add <file>        # stage a file
git add .             # stage all changes in current directory
git commit -m "msg"  # create a commit from staged changes
git commit --amend    # amend the most recent commit (use with care)
```

3) View history and details

```bash
git log --oneline --graph --decorate --all  # compact history graph
git show <commit>        # show a commit's content and metadata
git blame <file>         # show who changed each line last
```

---

## Branching and merging

```bash
git branch             # list local branches
git branch <name>      # create a new branch
git switch <name>      # switch to a branch (or `git checkout <name>`)
git switch -c <name>   # create + switch
git merge <branch>     # merge branch into current branch
git rebase <branch>    # replay commits onto another base (linearize history)
```

Tips:
- Use `merge` for straightforward merges. Use `rebase` when you want a linear
	history — avoid rebasing public branches that others use.

---

## Remotes and collaboration

```bash
git remote -v                     # show remotes
git remote add origin <url>       # add a remote
git fetch origin                  # fetch changes from remote
git pull origin main              # fetch + merge remote branch into current
git push origin <branch>          # push local branch to remote
```

If you created a repository on GitHub first, clone it and then add your files.

---

## Undoing and recovering

```bash
git restore <file>               # discard unstaged changes to a file
git restore --staged <file>      # unstage a staged file
git reset --soft <commit>        # move HEAD to commit, keep index
git reset --hard <commit>        # move HEAD and reset working tree (destructive)
git revert <commit>              # create a new commit that undoes a commit
git reflog                       # recover lost commits (shows HEAD movements)
```

Use `reset --hard` carefully — you can lose work.

---

## Stashing, tags, and ignore

```bash
git stash          # save local changes on a stack
git stash pop      # apply and remove stash

git tag v1.0.0     # create a lightweight tag
git tag -a v1.0.0 -m "release 1.0.0"  # annotated tag

# create a .gitignore file to exclude files (build artifacts, secrets)
# Example entries:
# node_modules/
# *.log
# .env
```

---

## Useful inspection commands

```bash
git ls-files          # list tracked files
git status --ignored  # show ignored files too
git show --name-only <commit>  # list files changed by a commit
```

---

## Advanced but handy

- `git cherry-pick <commit>` — apply a commit from another branch
- `git bisect` — binary search to find the commit that introduced a bug
- `git submodule` — include nested repositories (use sparingly)

---

## Recommended workflow (simple)

1. Create a feature branch: `git switch -c feature/xyz`
2. Work locally and commit in logical units: `git add` → `git commit`
3. Rebase onto the latest main if you need a clean history: `git fetch && git rebase origin/main`
4. Push your branch and open a pull request: `git push -u origin feature/xyz`

---

## Exercises

Practical exercises live in `EXERCISES.md` — they are ordered beginner → intermediate
and include verification steps and solutions.

---

## Further reading

- Pro Git book (free): https://git-scm.com/book/en/v2
- Git reference: https://git-scm.com/docs

---

If you'd like, I can:

- add more exercises and split them into `beginner`, `intermediate`, and `advanced` files,
- create small shell scripts that run example commands in a disposable repo,
- or add answers in a separate `SOLUTIONS.md` that can be hidden until you're ready.

Happy practicing!


