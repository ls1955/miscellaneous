```
git commit --amend # Modify latest commit

git push --force <repo> <branch> # RIP if somehow had worked after latest commit...

git push --force-with-lease <repo> <branch> # Safer. Will abort if there are changes after latest commit
```
