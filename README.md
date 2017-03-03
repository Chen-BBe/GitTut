# GitTut
For self-taught about github


![Overview of the Git data transport](https://github.com/Seven-Bi/GitTut/blob/master/images/git_data_transport.png)


Q1 in what case would be called either fork/clone/fetch?

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


Q2 what different between pull and rebase?

    Typically use of rebase could be first use git checkout feature branch (your branch), and
    then git rebase on the source branch (master), that would then iteratively place your
    changes on the latest commit history and insert the latest updates on source branch into
    your branch, which done the same thing as the git pull but with the good linear commit history.

- Could also check for [more details](https://www.derekgourlay.com/blog/git-when-to-merge-vs-when-to-rebase) by Derek Gourlay.


Q3 what different between reset hard and reset soft?


Q4 what different between checkout Head and checkout?


Q5 how are the relationships among workspace index repository?
