Git Commands
============

## Translated Versions
- [Vietnamese](READMEvi.md)
___

_Here are some Git tips I’ve learned._

*Note: This is not a fork from [Git-Commands](https://github.com/joshnh/bash_profile/blob/master/.bash_profile), but rather a few basic Git command usage tips that I've learned!*

---

### Registering with Git (If installed via [Git](https://git-scm.com))

| Command | Description |
| ------- | ----------- |
| `git config --global user.name "[username]"` | Tells Git your username (replace `[username]` with your desired username, can be the same as your Github username) |
| `git config --global user.email [email address]` | Tells Git your email address (it’s recommended to use the same email as your Git account) |
| `git config --system init.defaultbranch [branch]` | Changes the default branch in Git (Normally, Git defaults to `master`. If you encounter issues pushing because of a branch mismatch, use this command to set the default branch) |

### Starting with a Repo

| Command | Description |
| ------- | ----------- |
| `git init` | Use this if you’ve already created a repository on GitHub and are working on the project locally. It initializes a Git repository on your local machine. |
| `git remote add origin https://github.com/username/repository.git` | Links your local repository to the remote Git repository (allows you to push from local to Git) |
| `git pull origin [branch] --allow-unrelated-histories` | **NOTE:** Run this after the two above commands if your GitHub repository has files like `README`, `.gitignore`, etc. |
| `git clone https://github.com/username/repository.git` | Clone a repository from GitHub |

### Working with a Repo

| Command | Description |
| ------- | ----------- |
| `git status` | Check the status of the repo on local |
| `git add [file-name.txt]` | Add a specific file to the staging area |
| `git add -A` or `git add .` | Add all files to the staging area |
| `git commit -m "[commit message]"` | Add a commit message |
| `git rm -r [file-name.txt]` | Remove a file from both your local machine and staging area |
| `git rm --cached [file-name.txt]` | Remove a file from the staging area but keep it locally |
| `git remote -v` | Check the status of remote repositories |
| `git revert [commit-id]` | Does not delete the old commit but creates a new commit that "reverses" the content of the old commit. |

* **Tip:** ***If you’ve committed but haven’t pushed yet, you can use the following commands:***

| Command | Description |
| ------- | ----------- |
| `git reset --soft HEAD~1` | Undo the last commit and return files to an uncommitted state |
| `git reset --hard HEAD~1` | Undo the last commit and delete the files, which cannot be recovered |
| `git reflog` -> `git reset --hard [<HEAD code>]` | If you’ve used `--hard`, you can use these two commands to go back to the desired HEAD state |

### Branch & Merge (Recommended to merge on Git)

| Command | Description |
| ------- | ----------- |
| `git branch` | List all branches on Git |
| `git branch -a` | List all branches (local and remote) |
| `git branch [branch name]` | Create a new branch |
| `git branch -d [branch name]` | Delete a branch |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git checkout -b [branch name]` | Create a new branch and switch to it |
| `git checkout -b [branch name] origin/[branch name]` | Clone a branch from remote and switch to it |
| `git branch -m [old branch name] [new branch name]` | Rename a branch |
| `git checkout [branch name]` | Switch to another branch |
| `git checkout -` | Switch back to the last branch you were on |
| `git checkout -- [file-name.txt]` | Discard changes in a file |
| `git merge [branch name]` | Merge one branch into the current branch |
| `git merge [source branch] [target branch]` | Merge one branch into another branch |
| `git stash` | Temporarily save changes to files/folders |
| `git stash clear` | Discard saved changes |
| `git stash pop` | Restore saved changes |

* **Tip:** ***If you’re working in this branch but forget to switch branches and don’t want to lose changes, use `git stash`, checkout the other branch, then `pop` the changes back!***

### Update

| Command | Description |
| ------- | ----------- |
| `git push origin [branch name]` | Push a local branch to the selected remote branch |
| `git push -u origin [branch name]` | Push changes from local to remote and remember the branch for future pushes |
| `git push` | Push changes to the remote repository for the previously remembered branch |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git pull` | Update the local repository with the latest commits |
| `git pull origin [branch name]` | Pull changes from the selected remote branch to local |
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git` | Link local repository to remote via SSH |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set the SSH URL for the remote repository |

### Check & Compare

| Command | Description |
| ------- | ----------- |
| `git log` or `git reflog` | View changes in history |
| `git log --summary` | View detailed changes |
| `git log --oneline` | View concise changes |
| `git diff [source branch] [target branch]` | Preview changes before merging |

### Bonus

- The ENG translation was belongs to [ChatGPT](https://chatgpt.com)
- These are just a few commands you'll frequently use in Git. You can refer to other sources for more:
    - [Awesome Git Commands](https://github.com/onmyway133/awesome-git-commands)
    - [Atlassian Git](https://www.atlassian.com/git/tutorials/setting-up-a-repository)
    - [Git Game](https://github.com/git-game/git-game)
    - [Learn Git Branching](https://learngitbranching.js.org/)
