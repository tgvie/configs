# How to do things with Git

## Remote management

### View current remote url
`git remote -v`

### Disassociate an existing remote
`git remote rm {{name-of-remote-i.e.-origin}}`

### Associate a new remote
```
git remote add origin git@github.com:username/name-of-repo.git
git branch -M main
git push -u origin main
# or checkout existing branch
git checkout master
```

## Account management
### Change username for repo
`git config user.email "your_email@abc.com"`

### Set user for repository
```
git config user.name "Mona Lisa"
git config user.email "mona.lisa@example.com"
# Verify config
cat .git/config
```

## Branch management

### Push all branches to origin
`git push --all origin`

### Rename branch
`git branch -m old-branch new-branch-name`

## History management
### Delete all commit history
Deleting the .git folder may cause problems in your git repository. If you want to delete all your commit history but keep the code in its current state, it is very safe to do it as in the following:

Checkout: `git checkout --orphan latest_branch`

Add all the files: `git add -A`

Commit the changes: `git commit -am "commit message"`

Delete the branch: `git branch -D main`

Rename the current branch to main: `git branch -m main`

Finally, force update your repository: `git push -f origin main`

PS: this will not keep your old commit history around
