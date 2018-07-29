# git-cheatsheet
A cheat sheet for common and repeatedly used commands in **git** version control system.

<br>

## Clone

### Clone a whole repository (including all branches)..

```powershell
git clone <remote_repo_url> [<name_of_the_folder_to_clone_the_repo_in>]
```

<br>

### Clone a single branch from a remote repo (without inadvertently cloning the whole project)..

```powershell
git clone <remote_repo_url> --branch <name_of_desired_branch> --single-branch [<name_of_the_folder_to_clone_the_branch_in>]
```
- `--single-branch` flag is to prevent fetching all branches of the repo.

<br>

### Clone a specific tag from a remote repo..

```powershell
# Get the the whole repository first
git clone <remote_repo_url> [<name_of_the_folder_to_clone_the_repo_in>]

# After the clone, you can list the tags with 
git tag -n

# Then checkout a specific tag (See the next step first)
git checkout tags/<tag_name>

# Even better, checkout and create a branch (otherwise you will be on a branch named after the revision number of tag)
git checkout tags/<tag_name> -b <branch_name>
```
- [Source](https://goo.gl/qXqQNy)

<br>

## Pull

### Pull down, into the current branch, all changes that have been made to a specific remote branch..

```powershell
git pull origin <remote_branch_name>
```

**Example..**

1- First: move to your local branch that you want to pull updates to (say branch "dev" for example)..

```powershell
git checkout dev
```

2- Second: pull all changes from the **master** remote branch and merge it into the **dev** local branch..

```powershell
git pull origin master
```

<br>

## Push

### Push local changes up to a remote repository..

**Push a specific branch..**

```powershell
git push -u origin <branch_name>
```

<br>

**Push all branches..**

```powershell
git push -u origin --all
```

<br>

### Push local tags up to a remote repository..

**Push a specific tag..**

```powershell
git push -u origin <tag_name>
```

<br>

**Push all tags..**

```powershell
git push -u origin --tags
```

<br>

## Tag

### List all existing tags..

```powershell
git tag -n
```
The **`-n`** flag displays the first line of the annotation message along with the tag, or the first commit message line if the tag is not annotated.

<br>

### Create a tag..

**Create a tag to the current commit..**

```powershell
git tag -a <tag_name> -m "<tag_message>"
```

**Example..**

```powershell
git tag -a 1.0.0 -m "version 1.0.0"
```

<br>

**Create a tag to a specific commit..**

```powershell
git tag -a <tag_name> <commit_id> -m "<tag_message>"
```

**Example..**

```powershell
git tag -a 0.1.5 e3ef9dc -m "version 0.1.5"
```

<br>

**Clone a specific tag..**

See the [Clone a specific tag from a remote repo](#clone-a-specific-tag-from-a-remote-repo) section

<br>

## Branch

### Create a new branch of the branch you are currently on..

```powershell
git branch <branch_name>
```

<br>

### Rename the current branch
```powershell
git branch -m <new_name>
```

<br>

### Delete a branch

Note that you need to move to another branch first..

```powershell
git branch --delete <branch_name>
```

<br>

**Force delete un-merged branches..**

```powershell
git branch -D <branch_name>
```

<br>

**Delete a remote branch..**

```powershell
git push origin --delete <remote_branch_name>
```

<br>

### Switch to a specific branch..

```powershell
git checkout <branch_name>
```

<br>

### List all branches..

**List all local branches..**

```powershell
git branch
```

<br>

**List all local and remote branches..**

```powershell
git branch -a
```

<br>

## Merge

### Merge the specified local branch to the local branch you are on right now..

```powershell
git merge <local_branch_name>
```

<br>

### Merge the specified remote branch to the local branch you are on right now..

```powershell
git merge <remote_name>/<remote_branch_name>
```

<br>

## Add

### Stage all new, modified and deleted files..

```powershell
git add -all
# or
git add -A
```

<br>

### Stage all new and modified files, without deleted ones..

```powershell
git add .
```
Note the dot **`.`** in the end of the command.

<br>

### Stage all modified and deleted files, without new ones..

```powershell
git add -u
```

<br>

## Remote

### Show URL of the existing remote repository..

```powershell
git remote -v
```

<br>

### Change an existing URL of a remote repository..

```powershell
git remote set-url origin <new_remote_repository_url>
```

<br>

### Add URL for the remote repository where your local repository will be pushed..

```powershell
git remote add origin <remote_repository_url>
```

<br>

## How to ignore files that have already been committed to the repo?

```
git rm -r --cached .
git add .
git commit -m "Clean up ignored files"
```
[Source](https://www.git-tower.com/learn/git/faq/ignore-tracked-files-in-git)

<br>

## Various Things

### Adding an existing project to GitHub using the command line
See the complete guide here: [Adding an existing project to GitHub using the command line](https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/)

<br>

### Cloning a repository from GitHub using the command line
See the complete guide here: [Cloning a repository from GitHub using the command line](https://help.github.com/articles/cloning-a-repository)
