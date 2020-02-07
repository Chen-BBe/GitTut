## Branch


Combining the work from the multiple of branches together, this will allow us to branch off, develop a new feature, and then combine it back in.

For example, we have a Master branch and now it's on stage C then we create a feature branch based current stage C(a snapshot derived from A) and later
we developed D and E as we continued working on this feature branch.

![Upstream vs Origin](https://github.com/Seven-Bi/GitTut/blob/master/images/merge.png)

when we git merge will combine a sequences of commits into one unified history.


### Usage

merge a branch
- git checkout master
- git merge branch-name