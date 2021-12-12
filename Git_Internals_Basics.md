# Git Internals Basics

## Git Objects

Git is a *content-addressable filesystem*, which essentially means that in the core Git is a simple key-value data store.  
This basically means that you can insert any kind of content into a Git repository, for which git will hand you back a unique key you can use later to retrieve that content.
