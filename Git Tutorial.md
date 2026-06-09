
## Changing the last commit

`git commit --amend`

Add our missing file and run git commit --amend:
```
git add test4.md
git commit --amend
```

>[!warning] Remember to **only amend commits that have not been pushed anywhere**.

## Changing multiple commits

To modify commits further back in our history.

`git rebase -i HEAD~2 (to edit the last two commits)` : interactively stop after each commit we are trying to modify, and then make whatever changes we wish.

`edit` in `git rebase -i HEAD~2` stops at that commit and then that commit becomes your last commit so you can amend it and then continue rebasing rest of the commits with `git rebase --continue`.

>[!warning] If you have to rebase commits in a shared repository, make sure you're doing so for a very good reason that your coworkers are aware of.

You can think of `git reset --soft` as a more powerful amend. Instead of changing the last commit, you can go back multiple commits and combine all the changes included in them into one commit.

Similarly to `git commit --amend`, `git reset --hard` is a destructive command which overwrites history.

>[!warning]  **make sure you know exactly why you’re using it, and that your coworkers are also aware of how and why you’re using it.**

## Branches and pointers

>A branch is a pointer to a single commit.

Commit is a pointer that points to the commit that came before it!.

---

## Git Branching - Basic Branching and Merging

Why git works the way it does?

