# Git Cheat Sheet

## Normal uses
New commit
```bash
# Add all files in the current directory
git add .
git add -A #To delete also

# Commit staged changes with a message
git commit -m "Commit message"

# Push to remote
git push
```

Fix commit: make sure you can rewrite the commit history
```bash
# Add all files in the current directory
git add .
git add -A #To delete also

# Amend the last commit
git commit --amend -m "Updated commit message"

# Force push to remote
git push --force
```

## Setting Up

### Install Git
```bash
# Check if Git is installed
git --version
```

### Configure Git
```bash
# Set your username
git config --global user.name "Your Name"

# Set your email
git config --global user.email "your.email@example.com"

# Set default editor
git config --global core.editor "code --wait"

# View all configurations
git config --list
```

## Basic Commands

### Initialize a Repository
```bash
# Create a new Git repository
git init
```

### Clone a Repository
```bash
# Clone an existing repository
git clone https://github.com/username/repository.git

# Clone to a specific folder
git clone https://github.com/username/repository.git folder-name

# Clone a specific branch
git clone -b branch-name https://github.com/username/repository.git
```

### Check Status
```bash
# View the status of your working directory
git status
```

## Working with Changes

### Stage Changes
```bash
# Add a specific file to staging
git add filename.txt

# Add multiple files
git add file1.txt file2.txt

# Add all files in the current directory
git add .

# Add all files including deleted ones
git add -A

# Add modified and deleted files (but not new ones)
git add -u
```

### Commit Changes
```bash
# Commit staged changes with a message
git commit -m "Commit message"

# Add and commit all changes in one command
git commit -am "Commit message"

# Amend the last commit
git commit --amend -m "Updated commit message"
```

### View Changes
```bash
# View unstaged changes
git diff

# View staged changes
git diff --staged

# View changes between commits
git diff commit1 commit2

# View commit history
git log

#View last 5 commits

git log -n 5

#View las 5 commits and changes
git log -p -n 3

# View compact commit history
git log --oneline

# View graphical representation of commits
git log --graph --oneline --decorate --all
```

## Branches

### Manage Branches
```bash
# List all branches (* indicates current branch)
git branch

# List all remote branches
git branch -r

# List all branches (local and remote)
git branch -a

# Create a new branch
git branch branch-name

# Create a new branch and switch to it
git checkout -b branch-name

# Switch to a branch
git checkout branch-name

# Delete a branch (if merged)
git branch -d branch-name

# Force delete a branch (even if not merged)
git branch -D branch-name

# Rename current branch
git branch -m new-branch-name
```

## Merging and Rebasing

### Merge Branches
```bash
# Merge a branch into your current branch
git merge branch-name

# Merge with no fast forward
git merge --no-ff branch-name
```

### Handle Conflicts
```bash
# After resolving conflicts manually
git add .
git commit -m "Resolved conflicts"
```

### Rebase
```bash
# Rebase current branch onto another branch
git rebase branch-name

# Interactive rebase for the last n commits
git rebase -i HEAD~n
```

## Remote Repositories

### Manage Remotes
```bash
# List remote repositories
git remote -v

# Add a remote repository
git remote add origin https://github.com/username/repository.git

# Remove a remote
git remote remove origin

# Rename a remote
git remote rename old-name new-name
```

### Sync with Remote
```bash
# Fetch changes from remote (without merging)
git fetch origin

# Fetch changes from all remotes
git fetch --all

# Pull changes from remote (fetch and merge)
git pull

# Pull from specific remote and branch
git pull origin branch-name

# Push changes to remote
git push origin branch-name

# Push and set upstream branch
git push -u origin branch-name

# Force push (use with caution!)
git push -f origin branch-name

# Delete last commit pushed
git reset --soft HEAD~1
git push origin nombre-de-tu-rama --force
```

## Undoing Changes

### Discard Changes
```bash
# Discard changes in a file
git checkout -- filename.txt

# Discard all changes
git checkout -- .

# Restore file to a specific commit
git checkout commit-hash -- filename.txt
```

### Reset
```bash
# Unstage file (remove from staging area)
git reset filename.txt

# Unstage all files
git reset

# Reset to previous commit (keep changes in working directory)
git reset HEAD~1

# Reset to previous commit and discard changes
git reset --hard HEAD~1

# Reset to a specific commit
git reset --hard commit-hash
```

### Revert
```bash
# Create a new commit that undoes changes of a specific commit
git revert commit-hash
```

## Stashing

### Save and Apply Stashes
```bash
# Stash changes
git stash

# Stash changes with a message
git stash save "Work in progress for feature X"

# List stashes
git stash list

# Apply most recent stash
git stash apply

# Apply specific stash
git stash apply stash@{n}

# Apply and remove most recent stash
git stash pop

# Remove most recent stash
git stash drop

# Remove specific stash
git stash drop stash@{n}

# Clear all stashes
git stash clear
```

## Tags

### Manage Tags
```bash
# List all tags
git tag

# Create a lightweight tag
git tag tag-name

# Create an annotated tag
git tag -a tag-name -m "Tag message"

# Push tags to remote
git push origin tag-name

# Push all tags to remote
git push origin --tags

# Delete a tag
git tag -d tag-name

# Delete a remote tag
git push origin --delete tag-name
```

## Advanced Commands

### Cherry-pick
```bash
# Apply changes from a specific commit
git cherry-pick commit-hash
```

### Submodules
```bash
# Add a submodule
git submodule add https://github.com/username/repository.git path/to/submodule

# Initialize submodules
git submodule init

# Update submodules
git submodule update
```

### Clean
```bash
# Preview files that would be removed
git clean -n

# Remove untracked files
git clean -f

# Remove untracked files and directories
git clean -fd
```

### Reflog
```bash
# View reference logs
git reflog
```

### Bisect
```bash
# Start bisect session
git bisect start

# Mark current version as bad
git bisect bad

# Mark a known good commit
git bisect good commit-hash

# End bisect session
git bisect reset
```
```

This cheat sheet covers the most important Git commands a developer would need, including basic operations, branch management, remote repository interactions, and more advanced techniques. Feel free to expand it with any specific commands you find particularly useful in your workflow.