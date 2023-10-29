<!-- source: https://think-like-a-git.net/sections/testing-out-merges/the-savepoint-pattern.html -->

# Scenario
```
Want to merge branch `main` to 'feature'
```

# Steps
```bash
git checkout main # Ensure clean working state
git branch save_point # Create save_point branch (does not switch to it)
git merge feature # Resolve conflict, if any
# Predict the changes
git hist # View the changes
# if happy_with_result?
  git branch -d save_point
# else
  git reset --hard save_point
```
