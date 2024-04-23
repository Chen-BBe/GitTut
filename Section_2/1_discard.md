## How to discard to your git

### 4 scenarios
- Disk
- Staging
- Local
- Remote


#### Disk
This is what you daily will do to your code, you made some changes then `git diff` or `git status` you will see the changes are under `Changes not staged for commit`, in this scenarios you could `git checkout <changes_file>` or `git restore <changed_file>` if have latest git version to discard the changes.


#### Staging
Once command `git add` then changes now under `Changes to be committed` and now in the buffer, in this scenarios you could use `git reset <changed_file>` or `git restore --staged <changed_file>` to remove them from buffer but keep the changes in scenarios Disk

Or if you are about to remove changes both Disk and Staging then `git checkout HEAD <changed_file>`


#### Local
Then once command `git commit` then now the change become commit and in local git, then if only want to remove this commit in scenarios Local then can do `git reset --soft HEAD~1`, after that this commit gone but you still can find changes in scenarios Staging.

Or you want to remove both Local and Staging then do `git reset HEAD~1`, or even remove the change from all then do `git reset --hard HEAD~1`.

#### Remote
Last we `git push` then now the change is in public, we have to think about in a team environment, is this a feature or main or dev branch? is this branch only me or any other work on it?

note: consider use `git revert <any of commit in the tree>` or only the latest one `git revert HEAD~1` when you are not in feature branch, if this is a branch only you then can use `git reset ...` and `git push -f`