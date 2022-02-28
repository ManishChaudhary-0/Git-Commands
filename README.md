# Git Commands

### Getting & Creating Projects

| Command                                                           | Description                                |
| ----------------------------------------------------------------- | ------------------------------------------ |
| `git init`                                                        | Initialize a local Git repository          |
| `git clone ssh://git@github.com/[username]/[repository-name].git` | Create a local copy of a remote repository |

### Basic Snapshotting

| Command                            | Description                                                                |
| ---------------------------------- | -------------------------------------------------------------------------- |
| `git status`                       | Check status                                                               |
| `git add [file-name.txt]`          | Add a file to the staging area                                             |
| `git add -A`                       | Add all new and changed files to the staging area                          |
| `git add . `                       | Add all new and changes files in the current directory to the staging area |
| `git commit -m "[commit message]"` | Commit changes                                                             |
| `git rm -r [file-name.txt]`        | Remove a file (or folder)                                                  |

### Branching & Merging

| Command                                              | Description                                             |
| ---------------------------------------------------- | ------------------------------------------------------- |
| `git branch`                                         | List branches (the asterisk denotes the current branch) |
| `git branch -a`                                      | List all branches (local and remote)                    |
| `git branch [branch name]`                           | Create a new branch                                     |
| `git branch -d [branch name]`                        | Delete a branch                                         |
| `git push origin --delete [branch name]`             | Delete a remote branch                                  |
| `git checkout -b [branch name]`                      | Create a new branch and switch to it                    |
| `git checkout -b [branch name] origin/[branch name]` | Clone a remote branch and switch to it                  |
| `git branch -m [old branch name] [new branch name]`  | Rename a local branch                                   |
| `git checkout [branch name]`                         | Switch to a branch                                      |
| `git checkout -`                                     | Switch to the branch last checked out                   |
| `git checkout -- [file-name.txt]`                    | Discard changes to a file                               |
| `git merge [branch name]`                            | Merge a branch into the active branch                   |
| `git merge [source branch] [target branch]`          | Merge a branch into a target branch                     |
| `git stash`                                          | Stash changes in a dirty working directory              |
| `git stash clear`                                    | Remove all stashed entries                              |

### Sharing & Updating Projects

| Command                                                                           | Description                                                 |
| --------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| `git push origin [branch name]`                                                   | Push a branch to your remote repository                     |
| `git push -u origin [branch name]`                                                | Push changes to remote repository (and remember the branch) |
| `git push`                                                                        | Push changes to remote repository (remembered branch)       |
| `git push origin --delete [branch name]`                                          | Delete a remote branch                                      |
| `git pull`                                                                        | Update local repository to the newest commit                |
| `git pull origin [branch name]`                                                   | Pull changes from remote repository                         |
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git`     | Add a remote repository                                     |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH                     |

### Inspection & Comparison

| Command                                    | Description                    |
| ------------------------------------------ | ------------------------------ |
| `git log`                                  | View changes                   |
| `git log --summary`                        | View changes (detailed)        |
| `git log --oneline`                        | View changes (briefly)         |
| `git diff [source branch] [target branch]` | Preview changes before merging |

### Github for collaboration and working in a team with a shared repository

#### Team members

- Author - who owns an original github repositiry
- Contributor(s) - who aims to contributes to the author's repository

##### Steps for contributors

**Step 0:**
Before you make any changes make sure that you make changes into the latest version of your repository

```
git pull <author-repo-url> main
```

**Step 1:**

Fork the author’s repo to your own account.
This would create a repository in contributor’s GitHub account.

**Step 2:**
Clone the contributor’s GitHub repository to your local machine.

```
git clone <repo-url>
```

**Step 3:**
Create a new branch (Do not make changes on main branch)

```
git branch (To list all the branches)
git checkout -b <branch-name>
(To create a branch name and then switch to the branch name, e.g., git checkout checkout_error1)
```

**Step 4:**
Make necessary changes to the repository on local computer.

**Step 5:**
Add files

```
git add .
```

**Step 6:**
commit changes

```
git commit –m <commit message>
```

**Step 7:**
Push changes to the forked repository

```
git push <repo-url>
```

**Step 8:**
Create a pull request
Go to your forked repository. You may see a your recently pushed branches and so choose “compare and pull request”

##### Steps for an Author

**Step 1:**
From your project repository, checkout a new branch and test the changes

```
git checkout –b <contributorName-branchName> main
(e.g., git checkout –b ppankesh-test1 main)
git pull <contributor-repo-url> <branchName>
(e.g., git pull https://github.com/ppankesh/test-repository.git test1)
```

**Step 2:**
Merge the changes and update on Github

```
git checkout main

git merge –no-ff <author-branch>
(e.g., git merge –no-ff <author-branch>ppankesh-test1 )

git push origin main

```
