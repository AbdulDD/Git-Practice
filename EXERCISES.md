# Git-Practice — Exercises

This file contains progressive exercises to practice the essential Git commands.
Work through them in order. Try to solve without looking at the solutions, then
check the `Solutions` section when you're ready.

## Setup for exercises

Create a disposable folder for exercises so you can freely experiment:

```bash
mkdir ~/git-practice-test && cd ~/git-practice-test
```

You can remove this folder afterwards.

---

## Beginner exercises

1) Initialize a repo and make your first commit

- Goal: create a Git repository, add a file, and make an initial commit.
- Steps:
  - `git init`
  - create `README.md` with a short line
  - `git add README.md`
  - `git commit -m "Initial commit"`
- Verify: `git log --oneline` shows one commit.

2) Check status and create a .gitignore

- Goal: see untracked files and ignore temporary files.
- Steps:
  - create `temp.log` and `node_modules/` directory
  - run `git status`
  - create `.gitignore` with `temp.log` and `node_modules/`
  - `git add .gitignore` & `git commit -m "Add .gitignore"`
- Verify: `git status` no longer shows the ignored files.

3) Amend the last commit

- Goal: update the previous commit message or include a missed file.
- Steps:
  - edit `README.md` or add a new file
  - `git add` the changes
  - `git commit --amend --no-edit` (to add files) or `--amend -m "New message"`
- Verify: `git log -1` shows amended commit message or updated content.

---

## Intermediate exercises

4) Branching and merging

- Goal: create a branch, make a change, merge into main.
- Steps:
  - `git switch -c feature/hello`
  - create `hello.txt` and commit
  - `git switch main`
  - `git merge feature/hello`
- Verify: `git log --oneline --graph --decorate --all` shows the merge.

5) Rebase a feature branch onto updated main

- Goal: simulate updating main and rebasing the feature branch.
- Steps:
  - on `main`, add a new commit (e.g., modify README)
  - `git switch feature/hello`
  - `git rebase main`
- Verify: history shows feature commits replayed on top of latest main.

6) Undo a change safely

- Goal: practice `git restore`, `git reset`, and `git revert`.
- Steps:
  - make a change to `hello.txt` but don't stage it, run `git restore hello.txt`
  - stage a change and then `git restore --staged hello.txt` to unstage
  - commit a change, then `git revert <commit-hash>` to create a revert commit
- Verify: appropriate file contents and log entries show the undo operations.

---

## Advanced exercises

7) Use stash to save and apply changes

- Goal: stash local modifications and reapply them.
- Steps:
  - make changes to multiple files
  - `git stash`
  - `git stash list`
  - `git stash pop`
- Verify: files return to the stashed state after applying the stash.

8) Recover a deleted branch using reflog

- Goal: delete a branch and recover it using `reflog`.
- Steps:
  - create and switch to `temp-branch`, make a commit
  - `git switch main` and `git branch -D temp-branch`
  - use `git reflog` to find the branch tip and `git switch -c temp-branch <sha>` to recover
- Verify: branch restored and commits present.

9) Cherry-pick a commit from another branch

- Goal: apply a single commit from a branch to the current branch.
- Steps:
  - on `feature/hello` create a commit that modifies a file
  - `git switch main`
  - `git cherry-pick <commit-hash>`
- Verify: commit appears on main.

10) Tagging a release

- Goal: create an annotated tag and push it to remote (if remote exists).
- Steps:
  - `git tag -a v1.0 -m "v1.0 release"`
  - `git tag` to list tags
  - (optional) `git push origin v1.0`
- Verify: tag exists locally (and on remote if pushed).

---

## Solutions

Below are the canonical commands for each exercise (try solving first!).

1) Initialize repo and first commit

```bash
git init
echo "# Test repo" > README.md
git add README.md
git commit -m "Initial commit"
```

2) Check status and create .gitignore

```bash
touch temp.log
mkdir node_modules
git status
echo "temp.log" > .gitignore
echo "node_modules/" >> .gitignore
git add .gitignore
git commit -m "Add .gitignore"
```

3) Amend the last commit

```bash
# add a missed file
git add missed.txt
git commit --amend --no-edit
# or to change message
git commit --amend -m "Improved initial commit message"
```

4) Branch and merge

```bash
git switch -c feature/hello
echo "hello" > hello.txt
git add hello.txt
git commit -m "Add hello"
git switch main
git merge feature/hello
```

5) Rebase

```bash
# on main
echo "update" >> README.md
git add README.md
git commit -m "Update README on main"
# rebase feature
git switch feature/hello
git rebase main
```

6) Undoing changes

```bash
# discard unstaged
git restore hello.txt
# unstage
git restore --staged hello.txt
# revert commit
git revert <commit-hash>
```

7) Stash

```bash
# make changes
git stash
git stash list
git stash pop
```

8) Reflog recovery

```bash
git switch -c temp-branch
# make commit
git commit -am "temp"
git switch main
git branch -D temp-branch
# find SHA with reflog
git reflog
# recreate branch
git switch -c temp-branch <sha>
```

9) Cherry-pick

```bash
# from feature
git switch main
git cherry-pick <commit-hash>
```

10) Tagging

```bash
git tag -a v1.0 -m "v1.0"
git tag
# push tag if remote exists
# git push origin v1.0
```

---

If you'd like, I can also add a `SOLUTIONS.md` file and hide solutions behind a branch or an optional flag so you can practice without seeing answers immediately. Would you like that?