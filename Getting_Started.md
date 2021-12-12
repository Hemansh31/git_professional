# The why, what and how of Version Control System

## What's a Version Control and why use it?

1. It's a system taht records changes to a file or set of files so that we can recal specific versions later.

2. For Example if we were a graphic designer and we want to keep every version of an image or a layout we could use a version control system.

3. A VCS allows us to do the following things:
   1. Revert some selected files back to a previous state
   2. Revert entire project to a previous state
   3. Compare changes to the project over time
   4. Track the origin of changes and bugs if any
   5. File recovery becomes easy

### Local Version Control Systems

One common method of version control by many people is to copy files into another directory. This approach although simple is incredibly error prone since it's easy t forget which directory you're in and accidently write to the wrong file or copy over  files you don't mean to.

To deal with this issue, programmers long ago developed local VCSs that had a simple database that kept all the changes to files under revision control. For Example [RCS](https://www.gnu.org/software/rcs/)

### Centralized Version Control Systems

The next major issue people encounter is that they need to colloborate with developers on other systems. Centralized Version Control Sytems (CVSs) such as CVS, Subversion, and Perforce were developed to solve these issues. In CVSs a single server contains all the versioned files and a number of clients check out files from that central place.

CVSs are based on the idea that there is a single central copy of your project somewhere and programmers will commit their changes to this central copy.

Committing a change means recording the change in the central system, so that other programmers can see this change. They can also pull down the change and the version control tool will update the contents of any files that were changed.

The most obvious downside of this system is the single point of failure that the centralized server represents.

### Distributed Version Control Systems

In DVCs clients don't just check out the latest snapshot of the files but rather they fully mirror the repository including it's full history. This resolves the single point of failure problem of CVSs.

## What is Git?

Even though Git's user interface is fairly similar to other VCSs, Git stores and thinks about information in a very different way.

### Snapshots, Not Differences

**Delta Based Version Control** : Most other VCSs store information as a list of file based changes. They think of the information as a set of files and the changes made to each file over time.

**Snapshot Based Version Control** : Git thinks of it's data like a series of snapshots of a miniature filesystem. With Git every time you commit Git basically takes a picture of what all your files look like at that moment and stores a reference to that snapshot. Git thinks about it's data more like a stream of snapshots.

### Benefits of Git over other VCSs

1. Nearly all operations are local, thus there is no network latency overhead and hence you can work offline and commit changes easily to your local repo history and upload them later.

2. Everything in Git is checksummed before it is stored and is then referred to by that checksum. Git uses SHA-1 hash for this checksumming.

3. Git generally only adds data

4. Git has three states that the files can reside in *modified*, *staged*, and *committed*.
   1. Modifed means that you have changed the file but have not committed it to your database yet.
   2. Staged means that you have marked a modified file in its current version to go into your next commit snapshot.
   3. Committed means that the data is safely stored in your local database.  
