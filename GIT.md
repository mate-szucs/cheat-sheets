
git-bash: https://git-scm.com/downloads

https://nvie.com/posts/a-successful-git-branching-model/



git clone http://bitbucket.tonkatsu.local/scm/tks/tk-monorepo.git



git status

git config --local --list



(listaz)

git branch



uj brancs letrehozas

git checkout -b TKS-247



(develop)

git push origin



git fetch --all



letrehozza a remote origin szerveren a branch-et

git push origin TKS-247







git checkout develop

git pull

git checkout TKS-247



git rebase -i HEAD~3

git rebase -i develop abc123



git push origin abc123

pull req + 







(force push)

git push origin +TKS-247



drop all local changes (warning):
git reset --hard



Rebase own branch (from develop)
First of all, let's say the branch you are working on is "own_branch", and you want to keep it up to date with the branch "develop". 

This little guide will show you how to do that with PhpStorm: 

1. Checkout develop (with help of the right-bottom branch button)
2. Update your project (blue arrow at the right top of the screen)
3. With help of the bottom right branch options, select "own_branch" and click on "Checkout and Rebase onto current". 
4. Just push. (Do not pull)




# Rebase feature branch to develop
```
1. git rebase develop
2. (resolve conflict)
3. (git rebase --abort)
4. git push --force
```
# Rebase resolve conflict
```
1. git diff --name-only --diff-filter=U --relative
2. (edit files)
3. git add (conflictedFiles)
4. git rebase --continue
5. edit commit message (:q)
```


# Update project (svn up megfelelője)
https://happygitwithr.com/pull-tricky.html



# 1. stash:
```
git fetch
git stash save
git pull
git stash pop
(resolve conflict)
(git reset)
(git stash drop)
```
# 2. commit + merge
```
git commit
git fetch
git pull
(resolve conflict)
```
# 3. commit + rebase
```
git commit
git fetch
git pull --rebase
(git rebase --abort)
(OR 100 x resolve conflict)
```
# 4. tmp-branch + commit + checkout + (merge OR cherry-pick) ...
