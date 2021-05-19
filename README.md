  * [Destroy uncommit file / remove git branch /  remote url](#destroy-uncommit-file---remove-git-branch----remote-url)
  * [Show dot file](#show-dot-file)
  * [Server side make sure all commit are same](#server-side-make-sure-all-commit-are-same)
  * [Reset to last commit](#reset-to-last-commit)
  * [abort all commit after Merge](#abort-all-commit-after-merge)
  * [Update了 Github 沒有顯示當天的contributor紀錄](#update--github--------contributor--)
  * [Show .git config list](#show-git-config-list)
  * [View all remote url](#view-all-remote-url)
  * [Remove git record of the folder](#remove-git-record-of-the-folder)
  * [HEAD detached xxxxx](#head-detached-xxxxx)
  * [Remove remote and local branch](#remove-remote-and-local-branch)
  * [Remove remote url](#remove-remote-url)
  * [Fix last commit](#fix-last-commit)
  * [Revert last commit](#revert-last-commit)
  * [List all the remote branch](#list-all-the-remote-branch)
  * [Git stach](#git-stach)


### Destroy uncommit file / remove git branch /  remote url

```bash
git reset --hard HEAD
git remote -v 
git branch -D <branchName>
git push origin --delete <branchName> [delete branch remotely]
git remote set-url origin <https://>
```

### Show dot file

```bash
dir -A
ls -ld .?*
```

### Server side make sure all commit are same

```bash
git fetch origin master
git reset --hard FETCH_HEAD
```

### Reset to last commit

```sql
git reset --hard HEAD~1 
要注意使用這個 它會丟掉你現在做的東西
他這個 就是 他像去 github 那邊 拿最新的 commit 直接 放進你這裡
```

## abort all commit after Merge

```jsx
$ :qa!
$ git reset --hard HEAD
```

## Update了 Github 沒有顯示當天的contributor紀錄

1. check 你Github的 user 和 email

```jsx
$ git config user.name
$ git config user.email
```

 2.  新電腦的 user name 和 email 也要一樣 他才會在當天+contributor紀錄

Change name and email in new computer.

```jsx
$ git config --global user.name "step 1 origin name"
$ git config --global user.name "step 1 origin email"
```

## Show .git config list

可以看到 你的 username 那些資料

```bash
git config --list
```

## View all remote url

```bash
$ git remote -v
```

## Remove git record of the folder

remove components folder and push to remote then it will removed previous component folder.

```bash
$ git rm -r components 
// or
$ git rm -r components -f
```

## HEAD detached xxxxx

這個是說 你現在做什麼 他都不會upload 到最新的

你可以 **`git branch`** 看看下。

如果你是rollback去之前紀錄，你需要 `git checkout -b newBranch` 拿你rollback的資料

如果你不小心在 `HEAD detached` 想要跳出這個 就直接 `git checkout yourBranch` 就行了

## Remove remote and local branch

remote local branch

```bash
git branch -d branch_name
```

remove remote branch 

```bash
$ git push -d <remote_name> <branch_name>
$ git branch -d <branch_name>

// or specific the origin 
$ git push -d origin <branch_name>
```

## Remove remote url

```bash
$ git remote remove <remote_name>
```

## Fix last commit

```bash
$ git commit -a --amend
```

## Revert last commit

```bash
$ git revert HEAD
```

## List all the remote branch

```bash
git branch -r
```

## Git stach

checkout  to other branch but don't commit them. Store in local git

```bash
git stash save "some msg"
git show list
git stash show -p stash@{0} // check what change you made
```

applies the changes and leaves a `copy` in the stash

git stash list able to check the `statsh-name` eg:`stash@{0}` 

```bash
git stash apply STASH-NAME
```

applies the changes and **`removes`** the files from the stash

```bash
git stash pop STASH-NAME
```

remove stashed changes without applying them, run the command

```bash
git stash drop STASH-NAME
git stash clear // clear entire stach file
```
