# Introduction to Git

## Version Control

- **Local Version Control (LVCS)** - Database on a local hard drive that stores files and changes.
- **Centralized Version Control (CVCS)** - Single server storing all changes and files. Allows for teams to collaborate on large projects.
- **Distributed Version Coltrol (DVCS)** - System utilizing a server, as well as mirrored repositories on clients' machines. This overcomes the main vulnerability of a centralized version control system, in which a server going down prevents collaboration. In the worst case, a storage drive failure could risk the loss of a project in a centralized system. The mirrored repositories of a distributed version control system allow for easy recovery in case of server failure.

## What is Git?

Git is a DVCS that stores snapshots of changes as **commits**. Git allows for clients to work locally on parts of a project, and stores the entire project on a server. Since Git acts as a storage site for the project, it can **track all changes** and catch data loss or file corruption in transit.

Files in Git can reside in one of three main states:

- **Committed** - Data is securely stored in a local database
- **Modified** - File has been changed but not committed to the database
- **Staged** - Flagged a files's changed version to be comitted in the next snapshot

The flow goes, **checkout** a project, **modify** a project, **stage** your changes, **commit** changes to the repository, **push** your changes to the repository server. Multiple changes can be staged and committed all at once if you like. Upon pushing, all new commit messages get added to the repo commit record.

Git has desktop GUI's you can use. Find them [here](https://git-scm.com/downloads/guis). Github desktop suffices for this and is free. VSCode also has git integration that can help track changes.

## Getting Started With Git

git requires an initial configuration. To do this use:

```zsh
git config --global user.name "Your Name"
git config --global user.email "youremail@email.com"
```

These configurations set up your git "signature" for commits. This can be checked anytime using the command `git config --list`

## Setting up a Repository

There are two main ways to set up a repository for work in Git:

### Importing

An existing project can be imported into Git by navigating to the project directory and using the `$ git init` command.

### Cloning

To clone an existing repository from a server use the command:\
`git clone https://github.com/your-repo`

## Workflow in git

Files in Git are either **tracked** or **untracked**. Tracked files  are part of the most recent file snapshot, while untracked files are not. This most commonly happens when a client adds files to their local repo. Moving **untracked** files to the staging area will change their status to **tracked**.

The status of files in your repository can be checked anytime by using the command `$ git status`

### Tracking and Staging

A file can be staged and tracked using the `$git add <file>` command;

```zsh
#add single file
git add filename
#add all files
git add *
#add all files of a certain extension (.txt for example)
git add *.txt
```

These commands will **stage** files in the HEAD, to be **committed** when you choose.

### Commit Changes

When you've finished staging your changes, you can commit them using the command `git commit -m "made changes"`. This commits your changes to the repo, with a message "made changes" or whatever you want your commit message to say. **Try to make commit messages meaningful. Describe why you're making a change.**

### Push Changes

When you've committed all your changes locally, you'll be ready to **push** those changes to the repo server to be backed up and shared.

```zsh
git push origin master
```

This command will push your changes to the remote repository (default name origin for cloned repo's), specifically to branch "master" in this case. Ensure that the branch name is correct for where you want to push your changes!

## Remote Repositories

If your repo has a remote equivalent, you can view the names of connected remotes at any time by using the command:

```zsh
git remote -v
```

This will return a list of remote names, as well as their associated URLs.
