## Commit


A commit records a snapshot of all the files in your directory not just one of the changes. It's like a giant copy and paste, but even better!

Git wants to keep commits as lightweight as possible though, so it doesn't just blindly copy the entire directory every time you commit. It can (when possible) compress a commit as a set of changes and it would look like.

![Upstream vs Origin](https://github.com/Seven-Bi/GitTut/blob/master/images/commit.PNG)

Git also maintains a history of which commits were made when. That's why most commits have ancestor commits above them.

![Upstream vs Origin](https://github.com/Seven-Bi/GitTut/blob/master/images/git_log.PNG)

note: blob (binary large object) is the object type used to store the contents of each file in a repository.

It's a lot to take in, but for now you can think of commits as snapshots of the project. Commits are very lightweight and switching between them is wicked fast!


### Usage

save changes compare to previous snapshot
- git add your-project-path

commit your changes
- git commit -m 'a brief description for the snapshot'