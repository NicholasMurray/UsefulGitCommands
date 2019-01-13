# Useful Git Commands
A list of all the Git Commands that I find useful

## Repository

### Working with a remote repository
````
git remote add upstream git://github.com/diaspora/diaspora.git
````

## Status

### Current 
status
```
git status
```

## Commits

### To view commits on a branch
```
git log --graph the_branch_name
```

## Branches

### Create and checkout new branch
```
git checkout -b new_branch_name
```

### Create and checkout a new branch from a branch
```
git checkout -b new_branch_name dev_branch
```

### Delete unmerged local branch
```
git branch -D the_local_branch
```

### Rename current local branch
```
git branch -m new_branch_name
```

### Push local branch to remote Git repository
```
git push -u origin the_local_branch
```

### Create local branch that fetchs and tracks remote branch
```
git checkout --track origin/the_remote_branch
```

### Push local branch with detached head to remote Git repository
```
git push origin HEAD:the_local_branch
```

### Pull down all remote branches locally
```
git fetch --all  
git pull --all
```

### View all local branches including hidden branches
```
git branch -a
```

### View locally the remote branch
```
git checkout origin/the_remote_branch
```

### Work locally with the remote branch
```
git checkout -b the_remote_branch origin/the_remote_branch
```

## Inspecting Changes with Diffs

### Diff a modified file before staging
```
git diff path/to/file
```

### List file name and status differences between two branches
```
git diff --name-status branch_one..branch_two
```

### View line differences in a named file between two branches
```
git diff mybranch master -- myfile.css
```

### View side by side differences in difftool
```
git difftool path/to/file
```

## Unstaged Changes

### Discard a file with unstaged changes
```
git checkout path/to/file/to/revert
```

### Discard all unstaged changes
```
git checkout -- .
```

### Discard all uncommmited changes
```
git reset --hard
```

### Delete unstaged local files

#### Show files that will be deleted
```
git clean -f -n 
```

#### Delete files
```
git clean -f
```

#### Delete Directories
```
git clean -f -d
```

## Undo Add
```
git reset
```

## Commits

### Add and commit all modified files, but not newly created files
```
git commit -am  "commit message"
```

### View all commit messages in current branch
```
git cherry -v development current_branch
```

### List all files in commit
```
git show --name-only <sha>
```

## Revert Commit

### Revert back one local commit

```
git reset --hard HEAD~1
```

### Revert everything from the HEAD back to the commit hash

*This will revert everything from the HEAD back to the commit hash, meaning it will recreate that commit state in the working tree as if every commit since had been walked back. You can then commit the current tree, and it will create a brand new commit essentially equivalent to the commit you "reverted" to.*

```
git revert --no-commit 0766c053..HEAD
git commit
```

### Revert branch to preceeding commit 

#### Verify changes to make
```
git log --oneline  
git checkout HEAD~1  
git reset hard origin/master  
```

#### Switch branches to go back to the correct branch
```
git checkout development  
git checkout master  
git pull  
```

#### Revert commit and push to remote repository
```
git log  
git revert 9121c997065b043228763356865c307115c47538  
```
Type message and then esc, :x  
```
git push  
```

#### Reword current commit message

```
git commit --amend -m "New commit message"
git push --force origin current_branch_name
```

#### Reword previous commit message

List previous commits since branching
```
git cherry -v parent_branch
```

Enter interactive rebase for commit N (where N is the number of commits back)
```
git rebase -i HEAD~N
```

Enable INSERT or Replace mode and type reword as per instructions
```
reword
```

Then escape, write and quit
```
esc
:wq
```

Edit Commit message then escape, write and quit
```
esc
:wq
```

To quit the interactive rebase
```
esc
git rebase --abort
```

## Rebase

### Pull remote master updates (since branching) into local branch

```
git pull --rebase origin master
```

### Undo a rebase

First make a backup 
```
git tag BACKUP
```

If some goes wrong you can run
```
git reset --hard BACKUP
```

Use git relog to find the desired commit
```
git reflog
```

Then reset head to desired commit
```
git reset --hard HEAD@{5}
```

Or alternatively rebase saves your starting point to ORIG_HEAD so this command will revert to pre-rebase state
```
git reset --hard ORIG_HEAD
```

## Diffs

### Compare diffs side by side
```
git difftool  
```
Launch 'opendiff' [Y/n]: Y

## Merging

### Merge locally
```
git checkout local_branch_to_merge_into
git merge local_branch_to_merge
```

### To exit a merge
```
git reset --merge
```

### To undo a local merge

To find commit to revert to
```
git log
```

To revert to previous commit
```
git reset --hard hash_of_commit_to_revert_to
```

## Tracking

### Remove untracked files and directories

Dry run
```
git clean -dn
```

Perform delete of specfied untracked file or directoty
```
git clean -df directory/to/be/untracked/
```

Perform delete of all untracked
```
git clean -df 
```

### Overwrite remote with local

Overwrite remote branch with local branch
```
git push -f origin the_branch_name
```

### Untracking a file that is already tracked
```
git rm --cached path/to/file/to/stop/tracking  
git commit -m "Removed file that shouldn't be tracked"
```

## Remotes

### Print your remotes' fetch/push URLs.
```
git remote -v
```
