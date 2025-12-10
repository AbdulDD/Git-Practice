# Git-Practice — A compact practice book for Git

## Overview

- This repository is a complete guide to Git.

- Introduces you to lot of commands thatyou can practice

- Git has three levels:
    1. Local Repository
    2. Staging Area
    3. Remote Repository

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