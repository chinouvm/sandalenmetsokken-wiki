---
tags:
  - Coding
  - Git
  - Cheatsheet
---

# Git cheatsheet

_**Author**: Chinou van Maris_

---

A collection of the most used :material-git: git commands with descriptions on how to use them. Inspired by the [Atlassian](https://www.atlassian.com/nl) cheatsheet.

### Git basics

```shell
# Create empty Git repo in specified directory. Run with no args to initialize current directory as a Git repo.
git init <directory>

# Clone repo located at`<repo> onto local machine. Original repo can be located on the local filesystem or on a remote machine via HTTP or SSH.
git clone <repo>

# Define author name to be used for all commits in current repo. Devs commonly use --global flag to set config options for current user.
git config user.name <name>

# Stage all changes in <directory> for next commit. Replace <directory> with a <file> to change a specific file.
git add <directory>

# Commit the staged snapshot, but instead of launching a text editor, use <message> as the commit message.
git commit -m "<message>"

# List which files are staged, unstaged, and untracked.
git status

# Display the entire commit history using the default format. For customization see additional options.
git log

# Show unstaged changes between your index and working directory.
git diff
```

### Rewriting git history

```shell
# Replace the last commit with the staged changes and last commit combined. Use with nothing staged to edit the last commit’s message.
git commit --amend

# Rebase the current branch onto <base>. <base> can be a commit ID, branch name, a tag, or a relative reference to HEAD.
git rebase <base>

# Show a log of changes to the local repository’s HEAD. Add --relative-date flag to show date info or --all to show all refs.
git reflog
```

### Undoing changes

```shell
# Create new commit that undoes all of the changes made in <commit>, then apply it to the current branch.
git revert <commit>

# Remove <file> from the staging area, but leave the working directory  unchanged. This unstages a file without overwriting any changes.
git reset <file>

# Shows which files would be removed from working directory. Use the -f flag in place of the -n flag to execute the clean.
git clean -n
```

### Git branches

```shell
# List all of the branches in your repo. Add a <branch> argument to create a new branch with the name <branch>.
git branch

# Create and check out a new branch named <branch>. Drop the -b flag to checkout an existing branch.
git checkout -b <branch>

# Merge <branch> into the current branch.
git merge <branch>
```

### Remote repositories

```shell
# Create a new connection to a remote repo. After adding a remote, you can use <name> as a shortcut for <url> in other commands.
git remote add <name> <url>

# Fetches a specific <branch>, from the repo. Leave off <branch> to fetch all remote refs.
git fetch <remote> <branch>

# Pull the specified remote’s copy of current branch and immediately merge it into the local copy.
git pull <remote>

# Push the branch to <remote>, along with necessary commits and objects. Creates named branch in the remote repo if it doesn’t exist.
git push <remote> <branch>
```

---

## Additional Options

---

Extra git configurations options.

### Git config

```shell
# Define the author name to be used for all commits by the current user.
git config --global user.name <name>

# Define the author email to be used for all commits by the current user.
git config --global user.email <email>

# Create shortcut for a Git command. E.g. alias.glog “log --graph --oneline” will set ”git glog” equivalent to ”git log --graph --oneline.
git config --global alias.<alias-name> <git-command>

# Set text editor used by commands for all users on the machine. <editor> arg should be the command that launches the desired editor (e.g., vi).
git config --system core.editor <editor>

# Open the global configuration file in a text editor for manual editing.
git config --global --edit
```

### Git diff

```shell
# Show difference between working directory and last commit.
git diff head

# Show difference between staged changes and last commit
git diff --cached
```

### Git reset

```shell
# Reset staging area to match most recent commit, but leave the working directory unchanged
git reset

# Reset staging area and working directory to match most recent commit and !overwrites all changes! in the working directory
git reset --hard

# Move the current branch tip backward to <commit>, reset the staging area to match, but leave the working directory alone
git reset <commit>

# Same as previous, but resets both the staging area & working directory to  match. Deletes uncommitted changes, and all commits after <commit>.
git reset --hard <commit>
```

### Git log

```shell
# Limit number of commits by <limit>. E.g. ”git log -5” will limit to 5 commits.
git log --<limit>

# Condense each commit to a single line.
git log --oneline

# Display the full diff of each commit.
git log -p

# Include which files were altered and the relative number of lines that were added or deleted from each of them.
git log --stat

# Search for commits by a particular author (<pattern>).
git log --auhtor="<pattern>"

# Search for commits with a commit message that matches <pattern>.
git log --grep="<pattern>"

# Show commits that occur between <since> and <until>. Args can be a commit ID, branch name, HEAD, or any other kind of revision reference.
git log <since>..<until>

# Only display commits that have the specified file.
git log -- <file>

# --graph flag draws a text based graph of commits on left side of commit msgs. --decorate adds names of branches or tags of commits shown.
git log --graph --decorate
```

### Git rebase

```shell
# Interactively rebase current branch onto <base>. Launches editor to enter  commands for how each commit will be transferred to the new base.
git rebase -i <base>
```

### Git pull

```shell
# Fetch the remote’s copy of current branch and rebases it into the local  copy. Uses git rebase instead of merge to integrate the branches.
git pull --rebase <remote>
```

### Git push

```shell
# Forces the git push even if it results in a non-fast-forward merge. Do not use the --force flag unless you’re absolutely sure you know what you’re doing.
git push <remote> --force

# Push all of your local branches to the specified remote.
git push <remote> -all

# Tags aren’t automatically pushed when you push a branch or use the --all flag. The --tags flag sends all of your local tags to the remote repo.
git push <remote> --tags
```

---
