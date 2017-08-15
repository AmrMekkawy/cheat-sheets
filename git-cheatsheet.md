# git-cheatsheet
A cheat sheet for common and repeatedly used commands in **git** version control system.

## Clone

### Clone a whole repository (including all branches)..

```
git clone <remote_repo_url> [<name_of_the_folder_to_clone_the_repo_in>]
```

### Clone a single branch (without inadvertently cloning the whole project)..

```
git clone <remote_repo_url> --branch <name_of_desired_branch> --single-branch [<name_of_the_folder_to_clone_the_branch_in>]
```
`--single-branch` flag to prevent fetching of all branches of the repo.

## Pull

### Pull down all changes that have been made to a specific branch..

```
git pull origin <branch_name>
```

**Example..**

1- First: move to your local branch that called **master**..

```
git checkout master
```

2- Second: pull all changes from the **master** remote branch and merge it to the **master** local branch..

```
git pull origin master
```

## Push

### Push local changes up to a remote repository..

**Push a specific branch..**

```
git push -u origin <branch_name>
```

**Push all branches..**

```
git push -u origin --all
```

### Push local tags up to a remote repository..

**Push a specific tag..**

```
git push -u origin <tag_name>
```

**Push all tags..**

```
git push -u origin --tags
```

## Tag

### List all existing tags..

```
git tag -n
```
The **`-n`** flag displays the first line of the annotation message along with the tag, or the first commit message line if the tag is not annotated.

### Create a tag..

**Create a tag to the current commit..**

```
git tag -a <tag_name> -m "<tag_message>"
```

**Example..**

```
git tag -a 1.0.0 -m "version 1.0.0"
```

**Create a tag to a specific commit..**

```
git tag -a <tag_name> <commit_id> -m "<tag_message>"
```

**Example..**

```
git tag -a 0.1.5 e3ef9dc -m "version 0.1.5"
```

## Branch

### Create a new branch of the branch you are currently on..

```
git branch <branch_name>
```


### Rename the current branch
```
git branch -m <new_name>
```

### Delete a branch

Note that you need to move to another branch first..

```
git branch --delete <branch_name>
```

**Force delete un-merged branches..**

```
git branch -D <branch_name>
```

**Delete a remote branch..**

```
git push origin --delete <remote_branch_name>
```


### Switch to a specific branch..

```
git checkout <branch_name>
```

### List all branches..

**List all local branches..**

```
git branch
```

**List all local and remote branches..**

```
git branch -a
```

## Merge

### Merge the specified local branch to the local branch you are on right now..

```
git merge <local_branch_name>
```

### Merge the specified remote branch to the local branch you are on right now..

```
git merge <remote_name>/<remote_branch_name>
```

## Add

### Stage all new, modified and deleted files..

```
git add -all
# or
git add -A
```

### Stage all new and modified files, without deleted ones..

```
git add .
```
Note the dot **`.`** in the end of the command.

### Stage all modified and deleted files, without new ones..

```
git add -u
```

## Remote

### Show URL of the existing remote repository..

```
git remote -v
```

### Change an existing URL of a remote repository..

```
git remote set-url origin <new_remote_repository_url>
```

### Add URL for the remote repository where your local repository will be pushed..

```
git remote add origin <remote_repository_url>
```

## Various Things

### Adding an existing project to GitHub using the command line
See the complete guide here: [Adding an existing project to GitHub using the command line](https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/)


### Cloning a repository from GitHub using the command line
See the complete guide here: [Cloning a repository from GitHub using the command line](https://help.github.com/articles/cloning-a-repository)
