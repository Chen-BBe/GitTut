## Rebase use case 1


Interactive rebase 
Say you were working with a project and you found something wrong with your preious commits(not just last one), then dont be afraid of `rebase` you can use it make your commits record nice by using interactive rebase. (but backup your things before you do it!)
[check more with interactive rebase](https://git-scm.com/docs/git-rebase)

![Upstream vs Origin](https://github.com/Seven-Bi/GitTut/blob/master/images/rebase_case1.png)

### Usage
git rebase -i HEAD~3  -> check the last 3 commits or more, then
	1- mark commits by using the command listed in there
	2- wq and follow the instructions to amend the commits
	3- once done, git rebase --continue
	4- if the local git tracking is different than remote repo, then have to use push --force to update the remote repo
