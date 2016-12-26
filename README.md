# git-cheatsheet
A cheat sheet for common and repeatedly used commands in GIT version control system

## Adding an existing project to GitHub using the command line
See the complete guide here: [Adding an existing project to GitHub using the command line](https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/)


## Cloning a repository from GitHub using the command line
See the complete guide here: [Cloning a repository from GitHub using the command line](https://help.github.com/articles/cloning-a-repository)


## Pull down all changes that have been made to a specific branch
```
git pull origin <branch_name>

# example
# first: move to your local branch "master"
git checkout master
# second: pull all changes from the "master" remote branch and merge it to the "master" local branch
git pull origin master
```


## Push local changes up to the remote repository
```
# push a specific branch
git push -u origin <branch_name>

# push all branches
git push -u origin --all
```


## Push local tags up to the remote repository
```
# push a specific tag
git push -u origin <tag_name>

# push all tags
git push -u origin --tags
```


## Create a tag
```
# create a tag to the current commit
git tag -a <tag_name> -m "<tag_message>"

# example
git tag -a 1.0.0 -m "version 1.0.0"

# create a tag to a specific commit
git tag -a <tag_name> <commit_id> -m "<tag_message>"

# example
git tag -a 0.1.5 e3ef9dc -m "version 0.1.5"
```


## Create a new branch of the branch you are currently on
```
git branch <branch_name>
```


## Rename the current branch
```
git branch -m <new_name>
```


## Delete a branch
```
# you need to move to another branch first
git branch --delete <branch_name>

# force delete un-merged branches
git branch -D <branch_name>

# delete a remote branch
git push origin --delete <remote_branch_name>
```


## Switch to a specific branch
```
git checkout <branch_name>
```


## List all branches
```
# list all local branches
git branch

# list all local and remote branches
git branch -a
```


## Merge the specified local branch to the local branch you are on right now
```
git merge <local_branch_name>
```


## Merge the specified remote branch to the local branch you are on right now
```
git merge <remote_name>/<remote_branch_name>
```


## Stage all new, modified and deleted files
```
git add -all
# or
git add -A
```


## Stage all new and modified files, without deleted ones
```
git add .
```


## Stage all modified and deleted files, without new ones
```
git add -u
```


## Add URL for the remote repository where your local repository will be pushed
```
git remote add origin <remote_repository_url>
```


## Show URL of the existing remote repository
```
git remote -v
```


## Change URL of the remote repository
```
git remote set-url origin <new_remote_repository_url>
```



