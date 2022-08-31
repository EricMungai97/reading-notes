# Revisions and the Cloud

## **Version Control**

This is a system that allows you to revisit various versions of a fileor set files by recording changes.

 Helps *track modifications* and *compare changes*.

## **Centralized Version Control**

  Single server storing all changes and file versions and can be accessed by various clients.

## **Distributed Version Control**

  Addresses the major vulnerability of the CVS by helpin create mirrored repositories.

## ***Git***

  DVCS that stores data in a file system made up of snapshots. Basically createsa snapshot of the file and stores a reference to it.

It helps:

1. Track changes by tracking any change applied to any file.
2. Prevent the loss of data

File in Git reside in 3 main states:

- commited

- modified

- staged

## ***Git Commands***

Cloning

`git clone https://github.com/test`

Check file status

 `git status`

Tracking single file

`git add fiename`

Tracking all files

`git add.`

Tell if changes to be commited

`git status`

Committing a file

`git commit -m “made change x,y,z”`

Committing all changes

`git commit -a`

Pushing Changes

`git push origin master`

Seeing Remotes

`git remote`
