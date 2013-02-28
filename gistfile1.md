### Checkout a remote branch with tracking.
`git checkout --track -b <branch> origin/<branch>` -B to force it.

### Push a local branch for the first time.
`git push --set-upstream origin <branch>`<br>
`git push`

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

### Push local feature branch to upstream master
`git push origin feature-x:master`