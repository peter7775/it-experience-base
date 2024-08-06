### new branch based on current HEAD
`git branch <new-branch>`

### new branch based on some existing one
`git branch <new-branch> <base-branch>`

### new branch from a specific commit
`git branch <new-branch> f71ac24d`

### new branch from a specific tag
`git branch <new-branch> v1.2`

###  new branch from a remote branch
`git branch --track <new-branch> origin/<base-branch>`
 or
`git checkout --track origin/<base-branch>`

### new branch in a remote repository
`git push -u origin <local-branch>`

### list all local branches
`git branch --list`

### list all local and remote branches
`git branch -a`

### rename actual branch
`git branch -m new-name`

### rename some other branch
`git branch -m old-name new-name`

### remove your local branch if you have already pushed and merged it with the remote branch
`git branch -d branch_name`

### remove the local branch regardless of whether it’s been merged or not
`git branch -D branch_name`

### remove remote branch
`git push origin --delete branch_name`

* * *
https://www.git-tower.com/learn/git/faq/create-branch/
https://www.hostinger.com/tutorials/how-to-rename-a-git-branch/#How_to_Rename_a_Local_Git_Branch