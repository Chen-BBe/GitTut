## Branch


Branching means you diverge from the main line of development and continue to do work without messing with that main line.
Before we really dig into knowing how branch works and how to use it, we need to think about why we need branch with git.

Here is a basic example of using git branch, say we are runing a pizza store and receiving an order ask very special sauce, so 
in this case we have to ask a store member to make pizza as usual, but in the meantime chief will be developing this new recipe 
of sauce, then we will have a new branch for this feature(new sauce) beside master branch(make pizza).

![Upstream vs Origin](https://github.com/Seven-Bi/GitTut/blob/master/images/branch_1.png)

Eventually, chief will get the new feature done and put this new sauce on the pizza by merging these two branches, go check [merge.](./Section_1/4_merge.md)


### Usage

list all branches
- git branch

create an new branch
- git branch new-branch-name

switch to a branch
- git checkout branch-name

delete a branch
- git branch -d branch-name