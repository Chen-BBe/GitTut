# GitTut
for self-taught about github

-------------------------------------------------------------
## Overview
![alt text](https://github.com/Seven-Bi/GitTut/git_data_transport.png)


Q1 in what case would be called either fork/clone/fetch?

    fork actually create your own remote repo on your account called
    origin which a copy of the original repo but not really that one
    to keep track of the original repo, you need to add another remote
    named upstream, you will use upstream to fetch from the original repo
    in order to keep your local copy in sync with project you want to contribute
    to
    use origin to pull and push
    or contribute back to the upstream repo by making a pull request
    ![alt text](https://github.com/Seven-Bi/GitTut/upstream_origin.png)

    clone is actually copying the entire source repository locally,
    including all the history and branches, and this acts would normally be done
    after we fork the original repo on GitHub, otherwise you could simply
    clone from a original repo if you are not supposed to commit.

    fetch is about to create a copy for everything from a remote
    but without further acts not like pull will basically do
    fetch & merge


Q2 what different between pull and rebase?

Q3 what different between reset hard and reset soft?

Q4 what different between checkout Head and checkout?

Q5 how are the relationships among workspace index repository?
