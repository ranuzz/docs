## sync feature branch with base branch
in case base branch has been updated due to another feature branch merge


### Keep feature branch in sync
```sh
git checkout base_branch
git pull
git checkout feature_branch
git merge master

# resolve conflicts (if any)
git commit (if required)

git push origin feature_branch
```
