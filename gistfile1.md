### Checkout a remote branch with tracking.
`git checkout --track -b <branch> origin/<branch>` -B to force it.

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