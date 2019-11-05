![Overview of the Git data transport](https://github.com/Seven-Bi/GitTut/blob/master/images/git_data_transport.png)


## Q1 in what case would be called fork, clone or fetch?

    Fork actually create your own remote repo on your account called
    origin which a copy of the original repo but not really that one
    to keep track of the original repo, you need to add another remote
    named upstream, you will use upstream to fetch from the original repo
    in order to keep your local copy in sync with project you want to contribute
    to.
    Use origin to pull and push or contribute back to the upstream repo by making a pull request.


![Upstream vs Origin](https://github.com/Seven-Bi/GitTut/blob/master/images/upstream_origin.png)

    Clone is actually copying the entire source repository locally,
    including all the history and branches, and this acts would normally be done
    after we fork the original repo on GitHub, otherwise you could simply
    clone from a original repo if you are not supposed to commit.

    Fetch is about to create a copy for everything from a remote
    but without further acts not like pull will basically do
    fetch & merge.


## Q2 what difference between pull and rebase?

    Typically use of rebase could be first use git checkout feature branch (your branch), and
    then git rebase on the source branch (master), that would then iteratively place your
    changes on the latest commit history and insert the latest updates on source branch into
    your branch, which done the same thing as the git pull but with the good linear commit history.

- Could also check for [more details](https://www.derekgourlay.com/blog/git-when-to-merge-vs-when-to-rebase) by Derek Gourlay.


## Q3 what difference between reset hard and reset soft?

    When you modify a file in your repository, the change is initially unstaged.
    In order to commit it, you must stage it—that is, add it to the index—using git add.
    When you make a commit, the changes that are committed are those that have been added to the index.

    git reset changes, at minimum, where the current branch (HEAD) is pointing.
    The difference between --mixed and --soft is whether or not your index is also modified.
    So, if we're on branch  master with this series of commits:

##### - A - B - C (master)
    HEADpoints to C and the index matches C.

    When we run git reset --soft B, master (and thus HEAD) now points to B, but the index still has the changes from C;
    git status will show them as staged. So if we run git commit at this point, we'll get a new commit with the same
    changes as C.

Okay, so starting from here again:

##### - A - B - C (master)
    Now let's do git reset --mixed B. (Note: --mixed is the default option).
    Once again, master and  HEAD point to B, but this time the index is also modified to match B.
    If we run git commit at this point, nothing will happen since the index matches HEAD.
    We still have the changes in the working directory, but since they're not in the index, git status shows them as
    unstaged. To commit them, you would git add and then commit as usual.

    And finally, --hard is the same as --mixed (it changes your HEAD and index), except that --hard
    also modifies your working directory. If we're at C and run git reset --hard B, then the changes added in C,
    as well as any uncommitted changes you have, will be removed,
    and the files in your working copy will match commit B.
    Since you can permanently lose changes this way, you should always run git status before doing a hard
    reset to make sure your working
    directory is clean or that you're okay with losing your uncommitted changes.

##### Finally, a visualization:

![Upstream vs Origin](https://github.com/Seven-Bi/GitTut/blob/master/images/git_reset.png)

## Q4 what difference between rebase and merge? and when should we use which?

![Upstream vs Origin](https://github.com/Seven-Bi/GitTut/blob/master/images/rebase_merge.png)

## Q5 how should we handle the conflicts?

    When faced with a merge conflict, the first step is to understand what happened. 
    E.g.: Did one of your colleagues edit the same file on the same lines as you? 
    Did he delete a file that you modified? Did you both add a file with the same name?
    Git will tell you that you have "unmerged paths" (which is just another way of telling 
    you that you have one or more conflicts) via "git status" and you probably have seen 
    that a lot when you are here

    Now is the time to have a look at the contents of the conflicted file. Git was nice 
    enough to mark the problematic area in the file by enclosing it in 
    "<<<<<<< HEAD" and ">>>>>>> [other/branch/name]".

    Our job is now to clean up these lines: when we're done, the file should look exactly 
    as we want it to look. It can be necessary to consult the teammate who wrote the conflicting 
    changes to decide which code is finally correct. Maybe it's yours, maybe it's his - or maybe 
    a mixture between the two.

    What if you regret previous merge, don't worry too much .
    You should always keep in mind that you can return to the state before you started the merge 
    at any time. This should give you the confidence that you can't break anything. On the command 
    line, a simple "git merge --abort" will do this for you.

    In case you've made a mistake while resolving a conflict and realize this only after completing 
    the merge, you can still easily undo it: just roll back to the commit before the merge happened 
    with "git reset --hard " and start over again.

## Q6 how do we add current project to a remote repo?

    GitHub

        initialize your existing project $ git init
        add your files $ git add .
        giving your first commit $ git commit -m "init project to github"

        create new repo on GitHub account without README! and copy your remote url
        then $ git remote add origin + remote repo url

        check with $ git remote -v

        all right, final step $ git push origin master (your default remote main branch)


    Bitbucket

        basically, do the same steps as above
        but $ git push -u origin --all  #pushes up the repo and its refs for the first time
        $ git push origin --tags  #pushes up any tags

## Q7 when gitignore does not work?

    .gitignore only ignores files that are not part of the repository yet. If you already git added some files, their changes will still be tracked. 
    For the completely resolve this issue, it needs to delete those unnecessary files from remote repo by your hand and clear your cache by use git rm --cached on them (not from your file system).
     
