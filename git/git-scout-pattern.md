<!-- source: https://think-like-a-git.net/sections/testing-out-merges/the-scout-pattern.html -->

# Scenario
```
Want to merge branch `main` to `feature`
```

# Steps
```bash
git checkout main # Ensure clean working state
git checkout -b scout # Swicth to scout branch
git merge feature # Resolve merge conflict, if any
# if happy_with_result?
  # Meets up the main army with scout
  git checkout main
  git merge scout
# else
  # The scout died with honor...
  git checkout main
  git branch -D scout
```
