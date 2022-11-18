
## Three-way merges vs Fast forward
---
#### when three-way merges
![Upstream vs Origin](https://raw.githubusercontent.com/Chen-BBe/GitTut/master/images/three-way.png)

Three-way merges are a great way for you to keep track of important feature additions and development milestones in your project as they leave a visible merge commit in place when they’re used. However, they are not always so useful, especially if your project has a vast assortment of small commits happening at any given time that you’re not interested in recording.

For instance, bug fixes and other minor alterations to your project's code can quickly clutter up its history with an ever-expanding list of merge commits. Most of these commits don’t need to be tracked in this way and can instead be merged using Git's fast-forward merge algorithm.

#### when fast forward happens
When Git detects that your commit is about to be merged into your project's main branch without the main branch having been modified since your feature branch was first made, it chooses to use a fast-forward merge instead of a three-way merge. Fast-forward merges literally move your main branch's tip forward to the end of your feature branch. This keeps all commits created in your feature branch sequential while integrating it neatly back into your main branch.

Of course, this is not always a possibility with fast-moving projects being worked on by large, distributed teams. Instead, you can take advantage of rebasing operations to ensure your next commit can be completed with a clean fast forward.

if you really don't want anything else than a fast-forward merge, you can pass the --ff-only option to git merge. Git will abort the merge if a fast-foward is impossible.

#### when to do rebase
However, the Git merge --no-ff command merges the specified branch into the command in the current branch and ensures performing a merge commit even when it is a fast-forward merge. It helps in record-keeping of all performed merge commands in the concerning git repo.

---
##### quick tips:
- case-1, work on a independent feature implementation, more possibly use `three-way merges`
- case-2, work on a chunk of code changes to code base, may use `rebase` to make a clean line of commits