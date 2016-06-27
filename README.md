# Useful Git Commands
A list of all the Git Commands that I find useful

## Status

### Current branch status
git status

## Branches

### Create and checkout new branch
git checkout -b newbranch

### Delete unmerged local branch
git branch -D the_local_branch

### Rename current local branch
git branch -m newname

## Unstaged Changes

### Discard a file with unstaged changes
git checkout path/to/file/to/revert

### Discard all unstaged changes
git checkout -- .


## Merging

### To exit a merge
git reset --merge
