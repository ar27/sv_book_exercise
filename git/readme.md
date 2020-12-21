* How to force git to pull from the origin with no merge conflict
```git
git reset --hard origin/<branch_name>
```

* Get the current branch name/ changeset and last commit date and time information.
```git
git log -1
```

* How to unstage files:
```git
Git reset HEAD -- .
```

* How to uncommit files (without pushing) and keep the changes:
```git
Git reset --soft HEAD^
```

* How to add only tracked files:
```git
Git add -u
```

* How to unstage a file [(source):](https://stackoverflow.com/questions/6919121/why-are-there-two-ways-to-unstage-a-file-in-git) 
```git
git reset -- <filePath>
```

* How to compare files from two different branches [(source):](https://stackoverflow.com/questions/4099742/how-to-compare-files-from-two-different-branches)
```git
git diff mybranch master -- myfile.cs
```
----------
* Git merge without auto commit [(source):](https://stackoverflow.com/questions/8640887/git-merge-without-auto-commit)
```git
git merge <branch> --no-commit

//Or: 

git merge <branch> --no-commit --no-ff
//FF: fast forward
```
-----------
* Undo a Git merge that hasn't been pushed yet [(source):](https://stackoverflow.com/questions/2389361/undo-a-git-merge-that-hasnt-been-pushed-yet)
```git 
git reset --hard HEAD~1
```

* Git to omit deleted files [(source:)](https://stackoverflow.com/questions/3692152/suppressing-diffs-for-deleted-files-in-git)
```git
git diff --diff-filter=d
```

* Remove untracked files [(source):](https://www.hacksparrow.com/git/remove-untracked-files-and-directories.html):
```git
//if you want to decide
git clean -di
//get rid of everything
git clean -df
```

* How to squash with respect to the master[(source):](https://stackoverflow.com/questions/25356810/git-how-to-squash-all-commits-on-branch)
```git
git rebase -i master
```

Then follow the instruction. 
Change Pick to squash.
And the change your comment to whatever you desire.[source](https://stackoverflow.com/questions/5667884/how-to-squash-commits-in-git-after-they-have-been-pushed)

```git
git push --force origin my_branch
```



* Git  merge conflict: use
```git
-X theirs```


Destroy your local changes (anything that's not pushed) [source:](https://stackoverflow.com/questions/2452226/master-branch-and-origin-master-have-diverged-how-to-undiverge-branches/2452610)

	Ø git fetch
	Ø git reset --hard origin/master


* Amending commits: 
  Amend changes the commit hash
	Ø git add
	Ø git commit --amend


*Force pushing is required to update branches already pushed to the server (but it hasn’t been merged into integration) you will need to force push rebases, squashes, and amended commits since the commit hashes have changed.

	Ø git push -f


* Steps to Squashing a merged branch:

> git checkout feature/my-branch
> git checkout feature/my-branch
> git checkout -b feature/my-branch origin/integration
> git merge --squash feature/my-branch-orig
> git commit -m “MBE-1234: My feature”
> git push -f origin feature/my-branch



* Squashing 2 past commits together:
git rebase --interactive HEAD~2
Follow the rest as if it was any other squash. 

