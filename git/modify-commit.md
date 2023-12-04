```
# Latest commit
git commit --amend # Modify latest commit

# If already pushed
git push --force <repo> <branch> # RIP if somehow had worked after latest commit...

git push --force-with-lease <repo> <branch> # Safer. Will abort if there are changes after latest commit

# Old and pushed commit
git rebase -i HEAD~X
# X is the number of commits to go back

# Do the deed in interactive editor...

git push --force-with-lease <repo> <branch> # Probably not what you wanna do if there is somebody else working on the same branch
```
