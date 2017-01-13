# Useful Git Commands
A list of all the Git Commands that I find useful

## Repository

### Working with a remote repository
git remote add upstream git://github.com/diaspora/diaspora.git

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

### Push local branch to remote Git repository
git push -u origin the_local_branch

### Pull down all remote branches locally
git fetch --all  
git pull --all

### View all local branches including hidden branches
git branch -a

### View locally the remote branch
git checkout origin/the_remote_branch

### Work locally with the remote branch
git checkout -b the_remote_branch origin/the_remote_branch


## Inspecting Changes with Diffs

### List file name and status differences between two branches
git diff --name-status branch_one..branch_two

### View line differences in a named file between two branches
git diff mybranch master -- myfile.css


## Unstaged Changes

### Discard a file with unstaged changes
git checkout path/to/file/to/revert

### Discard all unstaged changes
git checkout -- .

### Discard all uncommmited changes
git reset --hard

### Delete unstaged local files
#### Show files that will be deleted
git clean -f -n 
#### Delete files
git clean -f

## Undo Add
git reset

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
