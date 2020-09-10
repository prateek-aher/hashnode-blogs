## The 3 Mistakes of My Git-Life

When I started learning about web development, I was advised by developers to start using [Git](https://git-scm.com/). In the first two weeks, I learned the basic commands and felt pretty confident using them. 

The rest of the month made me realize that some of my habits were not suitable for large projects. I decided to share my most prominent mistakes in this blog post so that no one else commits them. (pun intended)

## 1. Working directly on the master branch
You are oblivious to the concept of [Version Control](https://www.atlassian.com/git/tutorials/what-is-version-control) if you are in a team and `master` is the only branch you work on.
This is the case where everyone pushes their changes to the remote `master` only to discover a legion of conflicts. The proper solution for this mess is **branching**.

According to  [knittl](https://stackoverflow.com/users/112968/knittl)  on  [stackoverflow](https://stackoverflow.com/), 
> The `master` branch should represent the 'stable' history of your code. Use branches to experiment with new features, implement them, and when they have matured enough you can merge them back to `master`.
This way code in `master` will almost always build without problems and can be used directly for releases.

Creating a new branch is fairly simple. Let's say you have a bunch of commits already on `master` and you are going to be working on some issue no. 7. To create a new branch and switch to it at the same time, run the `git checkout` command with `-b` switch:
```git
$ git checkout -b issue7
Switched to a new branch "issue7"
```
which is the short version of:
```git
$ git branch issue7
$ git checkout issue7
```

## 2. Committing loads of changes in a single commit
I'm not the only one who does this, you know. 

Apart from the initial commit in your repo, your commits should contain only those changes which can be clearly defined in a single line message. In the process of making it short, don't do this:
```git
git commit -m "Did some changes"
# pushed 8 changed files to the repository
```
Trust me when I say that I used to do this 👆. Later when I came to review that commit I was like - "What animal leaves a message like that?". But don't go on and leave a  message worthy of 10 commits and 20 changed files. That's a bad practice too. Here, read  [Chris Beams](https://twitter.com/cbeams?s=20)' widely-referenced article on [how to write a Git commit message](https://chris.beams.io/posts/git-commit/).

> Commit brief, commit often.

The idea is to make it easier to revert a commit when things go sideways. Also, small commits are easier to understand when reviewing a pull request. Small commits are usually more focused and less broad than big commits.<br>
💡 **Not to mention:** It improves your contribution heatmap. 

## 3. Using shortcuts too much
Replacing long commands with custom shortcuts is useful, but it can lead to undesirable spinoffs. `git add .` is one of the commands that has troubled me most. I have to be careful with this one as it often adds unwanted files to the commit without me even noticing.

Git has a crazy command-line syntax. Some so-called “shortcuts” come with high tier commands: 
- `git pull` is exactly equivalent to `git fetch` followed by `git merge`. But try guessing the shortcut for `git branch` combined with `git checkout`. It is `git checkout -b`. (*I know, right?*)
- The semantics of some commands change completely when filenames are used with them. For example, `git commit` ignores local, unstaged changes in `binod.txt`. However, `git commit binod.txt` doesn’t.

Using shortcuts is a wonderful feature that saves time. But it can be a pain in the neck when it performs a bit too much than required. You then spend equal or more time executing commands that are harder to reverse.
Shortcuts always cost more.

And the man pages for these are so crappy. They describe the commands from the perspective of a Computer Scientist on steroids. Case in point: (thanks  [cgd](https://news.ycombinator.com/item?id=3680157))

> **git-rebase** – *Forward-port local commits to the updated upstream head*

**Translation**: Sequentially regenerate a series of commits so they can be applied directly to the head node


## Final thoughts
If you're a programmer or you work alongside programmers, chances are that you'll need to deal with a Version Control System someday. It is something you can’t do without if you have anything to do with writing code. 

Hence, it is best if you spend some time understanding what Git is and how it works. Read  [Pro Git](https://git-scm.com/book/en/v2), it is completely free to read.