# Useful Git Commands
A list of all the Git Commands that I find useful

## Status

### Current branch status
git status

## Branches

### Create and checkout new branch
git checkout -b newbranch

### Create and checkout a new branch from a branch
git checkout -b newbranch devbranch

### Delete unmerged local branch
git branch -D the_local_branch

### Rename current local branch
git branch -m newname

### Pull down all local remote branches
git branch -r | grep -v '\->' | while read remote; do git branch --track "${remote#origin/}" "$remote"; done  
git fetch --all  
git pull --all

## Unstaged Changes

### Discard a file with unstaged changes
git checkout path/to/file/to/revert

### Discard all unstaged changes
git checkout -- .

### Discard all uncommmited changes
git reset --hard

## Commits

### Add and commit all modified files, but not newly created files
git commit -am  "commit message"

### View all commit messages in current branch
git cherry -v master

## Diffs

### Compare diffs side by side
git difftool  
Launch 'opendiff' [Y/n]: Y

## Merging

### To exit a merge
git reset --merge

## Tracking

### Untracking a file that is already tracked
git rm --cached path/to/file/to/stop/tracking  
git commit -m "Removed file that shouldn't be tracked"

## Remotes

### Print your remotes' fetch/push URLs.
git remote -v
