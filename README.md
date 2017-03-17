# GitTut
For self-taught about github


![Overview of the Git data transport](https://github.com/Seven-Bi/GitTut/blob/master/images/git_data_transport.png)


## Q1 in what case would be called either fork/clone/fetch?

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


## Q2 what different between pull and rebase?

    Typically use of rebase could be first use git checkout feature branch (your branch), and
    then git rebase on the source branch (master), that would then iteratively place your
    changes on the latest commit history and insert the latest updates on source branch into
    your branch, which done the same thing as the git pull but with the good linear commit history.

- Could also check for [more details](https://www.derekgourlay.com/blog/git-when-to-merge-vs-when-to-rebase) by Derek Gourlay.


## Q3 what different between reset hard and reset soft?

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

####And finally, a visualization:

![Upstream vs Origin](https://github.com/Seven-Bi/GitTut/blob/master/images/git_reset.png)


## Q4 what different between checkout Head and checkout?


## Q5 how are the relationships among workspace index repository?
