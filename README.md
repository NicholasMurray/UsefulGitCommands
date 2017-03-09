# Useful Git Commands
A list of all the Git Commands that I find useful

## Repository

### Working with a remote repository
````
git remote add upstream git://github.com/diaspora/diaspora.git
````

## Status

### Current branch status
```
git status
```

## Branches

### Create and checkout new branch
```
git checkout -b newbranch
```

### Create and checkout a new branch from a branch
```
git checkout -b newbranch devbranch
```

### Delete unmerged local branch
```
git branch -D the_local_branch
```

### Rename current local branch
```
git branch -m newname
```

### Push local branch to remote Git repository
```
git push -u origin the_local_branch
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

## Revert Commit

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


## Diffs

### Compare diffs side by side
```
git difftool  
```
Launch 'opendiff' [Y/n]: Y

## Merging

### To exit a merge
```
git reset --merge
```

## Tracking

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
