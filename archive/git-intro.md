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

The flow goes, **checkout** a project, **modify** a project, **stage** your changes, **commit** changes to the repository server. Multiple changes can be staged and committed all at once if you like.

Git has desktop GUI's you can use. Find them [here](https://git-scm.com/downloads/guis). Github desktop suffices for this and is free.

## Using Git
