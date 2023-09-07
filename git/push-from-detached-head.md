# Scenario
Somehow working in a HEAD detached branch, wanna push
back to origin, then git output:
```
error: failed to push some refs to 'your-host.com:your-todo-app/main/feature-3000.git'
```

# Workaround
```
git checkout --detach # ensure we are at that HEAD detached branch
[change stuff && commit...]
git push origin HEAD:refs/heads/HEAD-detached-branch-name
```