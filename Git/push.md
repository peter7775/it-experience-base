### push from new local branch and make this branch on remote

`git push --set-upstream origin feature/BAT-11`

### push local branch featureB to remote branch featureBee

`git push origin featureB:featureBee`

### push one tag
`git push origin v1.5`

### push  all new tags
`git push origin --tags`

### remove remote branch
`git push origin --delete branch_name`


### force push (f.e. after rebase)

`git push -f`

https://stackoverflow.com/questions/22654056/how-to-push-to-remote-after-a-git-rebase