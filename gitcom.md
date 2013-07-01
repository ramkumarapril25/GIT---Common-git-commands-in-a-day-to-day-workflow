# Git Cheat Sheet

## Initial Setup

### [Initialize a repo](https://www.kernel.org/pub/software/scm/git/docs/git-init.html)
Create an empty git repo or reinitialize an existing one
```shell
$ git init
```

### [Fork a repo](https://help.github.com/articles/fork-a-repo#step-1-fork-the-spoon-knife-repository)
Click the "Fork" button at the top-right of any repository's GitHub page.

### [Clone a repo](https://www.kernel.org/pub/software/scm/git/docs/git-clone.html)
Clone the codepainter repo into a new directory called codepainter:
```shell
$ git clone https://github.com/jedhunsaker/codepainter.git codepainter
```

### [setup remotes](https://help.github.com/articles/fork-a-repo#step-3-configure-remotes)
```shell
$ git remote -v
$ git remote add upstream https://github.com/username/codepainter.git
$ git fetch upstream
```


## Every-day Commands

### [Branching](https://www.kernel.org/pub/software/scm/git/docs/git-checkout.html)

When working on a fork, you could be switching between different branches quite commonly. As such, you generally want to stay off the master branch and work on your own feature branches so that master is always clean and you can base new branches off of it.
```shell
$ git checkout -b feature_x
```

If upstream has a special develop branch or something, you can check that branch out separately, but setup tracking so you can sync it up from time to time. Like the master branch, don't work directly on this one. Try to keep it clean.
```shell
$ git checkout -b develop --track upstream/develop
```

Maybe you made some progress on a branch at work, but now you want to continue work at home. In that case, you're dealing with your own fork's branch, so you'll checkout from origin.
```shell
$ git checkout -b feature_x --track origin/feature_x
```

### [Switching Branches](https://www.kernel.org/pub/software/scm/git/docs/git-checkout.html)

Now, you can easily switch between branches with git checkout.
```shell
$ git checkout master
$ git checkout develop
$ git checkout feature_x
```

### [Status](https://www.kernel.org/pub/software/scm/git/docs/git-status.html)

Not sure if you're working on a clean branch? Want to see what files have changed? Git status will show you a report.
```shell
$ git status
```

### [Staging Changes](https://www.kernel.org/pub/software/scm/git/docs/git-add.html)

Now that you've added or modified some files, you need to stage those commits into "the staging area." Think of git commits like an array of airlock hatches on a space ship. On this space ship, you can only open the door to one airlock at a time. When you open the hatch, you can put stuff in or take stuff out at will. Not until you've closed the door have you committed those changes (git commit) and not until you hit the red button do all those hatches open up into space (git push).

You can stage inidividual files or all files at once.
```shell
$ git add foo.js
$ git add .
```

### [Unstaging Changes]()

Maybe you accidentally staged some files that you don't want to commit.

### [Commits](https://www.kernel.org/pub/software/scm/git/docs/git-commit.html)

Commit often. You can always squash down your commits before a push.
```shell
$ git commit 

### [Push](file:///C:/Users/Jed/AppData/Local/GitHub/PortableGit_ca477551eeb4aea0e4ae9fcd3358bd96720bb5c8/doc/git/html/git-push.html)
```shell
$ git push origin master


### Checkout a remote branch with tracking.
`git checkout --track -b <branch> origin/<branch>` -B to force it.

### Checkout fork's master branch with upstream/master as remote.
`git checkout -b master upstream/master`

### Push a local branch for the first time.
`git push --set-upstream origin <branch>`<br>
`git push`

### Push a local branch to a different remote branch.
`git push origin <local-branch>:<remote-branch>` -f to force it.

### Squash a number of commits into a single commit.
`git rebase -i HEAD~<number-of-commits>`

### Commit all changes with a message.
`git commit -am <msg>`

### Remove a local branch.
`git branch -d <local_branch>` -D to force it.

### Remove a remote branch.
`git push origin :<remote_branch>`

### Manually set tracking.
`git config branch.<local_branch>.remote origin`<br>
`git config branch.<local_branch>.merge refs/heads/<remote_branch>`

### Do a pull, stacking your recent commits on TOP of the pulled commits.
`git pull --rebase`

### Undo last push
`git reset --hard HEAD~1 && git push -f origin master`

### Rebase on upstream master
`git fetch upstream && git rebase upstream/master`

### List the set of repositories ("remotes") whose branches you track.
`git remote -v`

### Checkout as CRLF, Commit as LF
`git config --global core.autocrlf true`