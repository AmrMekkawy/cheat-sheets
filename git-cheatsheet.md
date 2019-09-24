# GIT Cheat Sheet
A cheat sheet for common and repeatedly used commands in **git** version control system.

<br>

## Clone

### Clone a whole repository (including all branches).

```shell
git clone <remote_repo_url> [<name_of_the_folder_to_clone_the_repo_in>]
```

Note that if you run `git branch` command which shows the local branches, you will only see `master` branch not all branches. To see all branches (local and remote), run this command `git branch --all`.

```shell
# Show all local and remote branches
git branch --all
```

And you can switch to any branch which you already have like this:

```shell
# Switch to another branch
git checkout <branch_name>
```

And you can repeat this command `git checkout <branch_name>` to show that branch locally.

More info, [check this answer](https://stackoverflow.com/questions/67699/how-to-clone-all-remote-branches-in-git/27020944#27020944).

<br>

### Clone a single branch from a remote repo (without inadvertently cloning the whole project).

```shell
git clone <remote_repo_url> --branch <name_of_desired_branch> --single-branch [<name_of_the_folder_to_clone_the_branch_in>]
```
- `--single-branch` flag is to prevent fetching all branches of the repo.

<br>

### Clone a specific tag from a remote repo.

```shell
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

### Pull down, into the current branch, all changes that have been made to a specific remote branch.

```shell
git pull origin <remote_branch_name>
```

**Example..**

1- First: move to your local branch that you want to pull updates to (say branch "dev" for example)..

```shell
git checkout dev
```

2- Second: pull all changes from the **master** remote branch and merge it into the **dev** local branch..

```shell
git pull origin master
```

<br>

## Push

### Push local changes up to a remote repository..

**Push a specific branch..**

```shell
git push -u origin <branch_name>
```

<br>

**Push all branches..**

```shell
git push -u origin --all
```

<br>

### Push local tags up to a remote repository..

**Push a specific tag..**

```shell
git push -u origin <tag_name>
```

<br>

**Push all tags..**

```shell
git push -u origin --tags
```

<br>

## Tag

### List all existing tags..

```shell
git tag -n
```
The **`-n`** flag displays the first line of the annotation message along with the tag, or the first commit message line if the tag is not annotated.

<br>

### Create a tag..

**Create a tag to the current commit..**

```shell
git tag -a <tag_name> -m "<tag_message>"
```

**Example..**

```shell
git tag -a 1.0.0 -m "version 1.0.0"
```

<br>

**Create a tag to a specific commit..**

```shell
git tag -a <tag_name> <commit_id> -m "<tag_message>"
```

**Example..**

```shell
git tag -a 0.1.5 e3ef9dc -m "version 0.1.5"
```

<br>

**Delete a local tag..**

```
git tag --delete tag_name_here
```

<br>

**Delete a remote tag..**

```
git push --delete origin tag_name_here
```

<br>

**Clone a specific tag..**

See the [Clone a specific tag from a remote repo](#clone-a-specific-tag-from-a-remote-repo) section

<br>

## Branch

### Create a new branch of the branch you are currently on..

```shell
git branch <branch_name>
```

<br>

### Create a new branch of the branch you are currently on and switch to it directly

```shell
git checkout -b <branch_name>
```

<br>

### Rename the current branch
```shell
git branch -m <new_name>
```

<br>

### Delete a branch

Note that you need to move to another branch first..

```shell
git branch --delete <branch_name>
```

<br>

**Force delete un-merged branches..**

```shell
git branch -D <branch_name>
```

<br>

**Delete a remote branch..**

```shell
git push origin --delete <remote_branch_name>
```

<br>

### Switch to a specific branch..

```shell
git checkout <branch_name>
```

<br>

### List all branches..

**List all local branches..**

```shell
git branch
```

<br>

**List all local and remote branches..**

```shell
git branch -a
```

<br>

## Merge

### Merge the specified local branch to the local branch you are on right now..

```shell
git merge <local_branch_name>
```

<br>

### Merge the specified remote branch to the local branch you are on right now..

```shell
git merge <remote_name>/<remote_branch_name>
```

<br>

## Add

### Stage all new, modified and deleted files..

```shell
git add -all
# or
git add -A
```

<br>

### Stage all new and modified files, without deleted ones..

```shell
git add .
```
Note the dot **`.`** in the end of the command.

<br>

### Stage all modified and deleted files, without new ones..

```shell
git add -u
```

<br>

## Remote

### Show URL of the existing remote repository..

```shell
git remote -v
```

<br>

### Change an existing URL of a remote repository..

```shell
git remote set-url origin <new_remote_repository_url>
```

<br>

### Add URL for the remote repository where your local repository will be pushed..

```shell
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


## Config

### How to list all configs of your git?

```shell
# List all configs of git
git config --list
```

```shell
# List local (project level) configs of git
git config --local --list
```

```shell
# List global configs of git
git config --global --list
```

<br>

### How to globally set your account's default identity?

```shell
# Go to your HOME folder
cd ~/

# Run the config commands that you need
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

<br>

### How to set your account's identity only in current repository?

```shell
# Go to the root directory of your project/repository
cd /path/to/the/root/directory/of/your/project/

# Run the config commands that you need
git config user.name "Your Name"
git config user.email "you@example.com"
```

<br>

### How to remove config settings?

```shell
# Remove a local config settings item
git config --local --unset-all user.name
```

```shell
# Remove a global config settings item
git config --global --unset-all user.name
```

Note that: `--unset` flag is used to remove **the line** matching the key from config file and `--unset-all` flag is used to remove **all lines** matching the key from config file.

<br>

### How to open local and global `.gitconfig` file?

```shell
# Steps to open your local .gitconfig file
cd /path/to/the/root/directory/of/your/project/
git config --local --edit
```

```shell
# Steps to open your global .gitconfig file
git config --global --edit
```

When running any of the above commands, the `.gitconfig` file will be opened in your default code editor.

<br>

## Miscellaneous

### Adding an existing project to GitHub using the command line
See the complete guide here: [Adding an existing project to GitHub using the command line](https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/)

<br>

### Cloning a repository from GitHub using the command line
See the complete guide here: [Cloning a repository from GitHub using the command line](https://help.github.com/articles/cloning-a-repository)

<br>

### Unlinking a locally cloned repository from its GitHub origin
See: [Unlinking a locally cloned repository from its GitHub origin](https://stackoverflow.com/a/23788536/458204) and [Removing a remote](https://help.github.com/articles/removing-a-remote/)

<br>

### How to undo the most recent commits in Git?
[See this answer on stackoverflow.com](https://stackoverflow.com/a/6866485/458204)