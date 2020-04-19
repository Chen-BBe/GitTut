## Rebase

The second way of combining work between branches is rebasing. Rebasing essentially takes a set of commits, "copies" them, and plops them down somewhere else.

Take a quick overview of rebase vs merge below

![Upstream vs Origin](https://github.com/Seven-Bi/GitTut/blob/master/images/rebase_introduction.PNG)


While this sounds confusing, the advantage of rebasing is that it can be used to make a nice linear sequence of commits. The commit log / history of the repository will be a lot cleaner if only rebasing is allowed.

However, **be aware to use rebase in a team unless you know what you are doing and working with.


### Usage
- git checkout feature_branch
- git rebase master