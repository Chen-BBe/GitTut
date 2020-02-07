## Sequence


Here I am going to introduce an idea I personally feel it really helps to understand how git works, that is "sequence".
In my opinion sequence is for describing a series of things like one following another, in git this is saying one "commit"
following another "commit" and each commit is a record of a speicial change and the "commit" will help us checking back whenever
we need.

let's quick have a look here.
![Upstream vs Origin](https://github.com/Seven-Bi/GitTut/blob/master/images/solo_branch.png)

just ignore the term "master", we will talk about it later.
each circle represents a "commit" and the sequential of commits form a "sequence", it seems like a solo workflow but with the 
"commit" this idea will fit any project that you want to track of and any change you did will be able to check/recover back by looking 
up your commit.

For how commit helps us with this, go check [commit.](./Section_1/2_commit.md)