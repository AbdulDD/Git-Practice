# Git-Practice — A compact practice book for Git

## Overview

- This repository is a complete guide to Git.

- Introduces you to lot of commands thatyou can practice

- Git has three levels:
    1. working directory
    2. Staging Area (after add)
    3. Local Repository (after commit)
    4. Remote Repository

- **Add** is staging the changes/updates in directory.
- **Commit** is saving the changes,updates,new iles and deletion into local repository.
- **Tags** are labels for releases/ important commits

---

## Basic Commands:

1. ```git init``` - we run the command in terminal in the directory "A", if we want to convert that directory "A" into a repository. Note it just initializaes the repository so still we eed to add and commit.

2. ```git clone http://repository/username/repo.git``` is used to clone the repository.

## Add commands:
1. ```git add . ``` adds all changes in current directory
2. ```git add * ``` adds all files except hidden ones
3. ```git add <filename>``` adds specific file changes
4. ```git add <dir>``` adds the change that were made in the specific directory
5. ```git add -u``` adds only uddate and deletion (no new files)
6. ```git add -p``` adds interactivly 

## Status commands:
1. ```git status ``` shows full status of chnages
2. ```git status -s``` shows symbolic information about changes
3. ```git staus -sb``` shows status + branch information
4. ```git status --ignored``` shows status of ignore files

## Commit commands:
1. ```git commit -m "message" ``` commits with message
2. ```git commit -am "message"``` commits only tracked and updates, no new files are commited
3. ```git commit --amend -m "new msg" ``` changes the last message
4. ```git commit -a``` commits only tracked changes
5. ```git commit --dry-run``` do not commits but only show what is in staging ared ready to be commited

## Tags:
1. ```git tag <version say V1.0> ``` creates a tag
2. ```git tag -a <version> -m "First release" ``` cretes a tag with label
3. ```git push --tags``` pushes tags to the remote repoitory
4. ```git push origin version ``` pushes spesific tag