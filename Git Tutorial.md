
## git commit --amend

```git
git add test4.md
git commit --amend
```

We updated the staging area to include the missing file, and then we replaced the last commit with our new one to include the missing file.

>Remember to only amend commits that have not been pushed anywhere!

>[!warning] `git commit --amend` does not edit the last commit, it *replaces that commit with an entirely new one.* This means that you could potentially destroy a commit other developers are basing their work on.

## git rebase

`git rebase -i` allows us to interactively stop after each commit we're trying to modify, and then make whatever changes we wish.

`git rebase -i HEAD~2` will rebase 2 commits.

To rebase back to the root `git rebase -i --root`.

### squash

>to keep our history clean. When feature is in development this history is important but after its merged into the main branch clean up history with squash.



