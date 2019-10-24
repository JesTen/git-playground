# Git commands

## Branches
[Git feature branch workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow)
| Command | Explanation |
|---------|-------------|
| `git checkout -b [branch_name]` | Checkout new branch |
| `git branch` | List local branches and highlight current |
| `git branch -a` | List local and remote branches |
| `git branch -r` | List remote branches |
| `git branch -d [branch_name]` | Delete branch |

## Adding
| Command | Explanation |
| ------- | ----------- |
| `git status` | Show files with changes. Show staged and unstaged files. |
| `git add -A` | Stage all files (make it available for commiting). |
| `git add .` | Stage all files in current folder. |
| `git add <file>` | Stage one file. |
| `git checkout <file>` | Undo all changes in file. |
| `git reset HEAD <file>` | Unstage file. (make it unavailable for committing). |

## Commits
| Command | Explanation |
|---------|-------------|
| `git commit` | Add commit message and body(optional). i = interactive (enable editing), w = write (save), q = quit. esc + ":" to enter "options mode"  |
| `git commit -m` | Add commit message |
| `git commit --amend` | Add files or change commit message to your last commit. |
| `git diff` | Shows the changes you've made. Always do this before committing to review yourself. |
| `git diff --staged` | Shows the changes of the staged files. |

## Push & pull
| Command | Explanation |
| ------- | ----------- |
| `git push <REMOTENAME> <BRANCHNAME>` | E.g. remotename = origin, branchname = master |
| origin (not a command) | alias on your system for an url of a particular remote repo. Git uses origin by default when pushing and pulling. |
| `git remote -v` | Show remote url (origin). |
| `git fetch` | Fetch changes without merging them to branch. E.g. fetch remote branches without merging them into the current branch. |
| `git pull` | Does git fetch and then git merge. |
| `git push <REMOTENAME> <BRANCHNAME> --force` | Do not use the --force flag unless you’re absolutely sure you know what you’re doing. It overwrites the remote with your local changes. |


## Reverting and resetting
| Command | Explanation |
|---------|-------------|
| `git reset HEAD^` | Move HEAD to the previous commit. It will undo the current commit but keep the changes. Rewrites history. (HEAD is a symbolic reference to the currently active branch.) |
| `git reset --hard HEAD^` | BE CAREFUL! Will remove the previous commit and it's changes permanently. |
| `git revert` | Creates new commit that undoes the changes from a previous commit. Adds history. |

## Logging
| Command | Explanation |
|---------|-------------|
| `git reflog` | Reflog is a mechanism to record when the tip of branches are updated. This command is to manage the information recorded in it. |
| `git log` | Prints out all commits. |
| `git log --oneline` | Prints out all commits in a short format. |
| `git log --graph --oneline --all` | Shows the commit tree ( like in git extensions or sourcetree) |

## Stashing
| Command | Explanation |
|---------|-------------|
| `git stash` | Stash the changes |
| `git stash save "Name of stash"` | Stash the changes with custom comment |
| `git stash list` | Lists the stash |
| `git stash apply` | Applies the lastest (keeps a copy in the stash). Git assumes you want o apply the lastest |
| `git stash apply stash@{2}` | Applies the given stash. (keeps a copy in the stash). |
| `git stash pop` | Apply and remove the lastest stash. |
| `git stash drop stash@{1}` | Removes the given stash. |

## Merging
| Command | Explanation |
|---------|-------------|
| `git merge` | Reapply commits on top of another base tip. Warning: Running git merge with uncommitted changes is discouraged: while possible, it leaves you in a state that is hard to back out of in the case of a conflict. |
| `git merge --abort`| Aborts the merge process (that has conflicts) and tries to reconstruct the pre-merge state  |

## Checking out commit SHA
| Command | Explanation |
|---------|-------------|
| `git checkout 56a4e5c08` | Checks out commit and triggers 'detached head' state. Changes done to a commit in this state does NOT belong to any branch. Can happen while rebaseing as it temporarily creates a 'detach head' state while running. |







