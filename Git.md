# Git cheatsheet

## Commits

Commit 

```
git commit
```

Detached HEAD

```
git check <commit_hash>
```

HEAD: Currently checkout commit

Check the logs

```
git log
```

Go back one commit from a branch

```
git checkout <branch_name>^
## Works also with ^^, ^^^,...
```

Go back one commit from current commit

```
git checkout HEAD^
## Works also with ^^, ^^^,...
```

Go back several commit

```
git checkout <commit_branch_head>~<number>
```

## Branches

branch early, and branch often 

Create a branch and move to it

```
git branch <branch_name>
git checkout <branch_name>
```

or 

```
git checkout -b <branch_name>
```

Merge branches

```
# When on the branch (with a *)
git merge <branch_name>
```

Git Rebase (Keep the commit history instead of a simple merge)

```
git rebase <branch_name>
```

Branch forcing

Reassigne a branch 

```
git branch -f <branch_name> <commit>
```
