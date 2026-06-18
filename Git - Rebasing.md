
With `rebase` command, you can take all the  changes that were committed on one branch and replay them on a different branch.

For example: You would check out the `experiment` branch, and then rebase it onto the `main` branch as follows:
```
git checkout experiment
git rebase main
```

