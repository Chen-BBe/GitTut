## Merge advance --no-ff


By default, the git merge command is a fast-forward merge. A fast-forward merge is possible when there is a linear path from the current tip to the target branch tip (A branch tip is the last commit or most recent commit on a branch).


However, the Git merge --no-ff command merges the specified branch into the command in the current branch and ensures performing a merge commit even when it is a fast-forward merge. It helps in record-keeping of all performed merge commands in the concerning git repo.


![Upstream vs Origin](https://raw.githubusercontent.com/Chen-BBe/GitTut/master/images/--no-ff.png)
