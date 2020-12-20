*How to force git to pull from the origin with no merge conflict
```git
git reset --hard origin/<branch_name>
```


```git
git log -1
```

Tells you information about your current branch and revision. 



Unstage files:
```git
Git reset HEAD -- .
```

How to uncommit files and keep the changes:
```git
Git reset --soft HEAD^
```

How to add only tracked files:
```git
Git add -u
```


How to unstage a file: 
```git
git reset -- <filePath>
```
From <https://stackoverflow.com/questions/6919121/why-are-there-two-ways-to-unstage-a-file-in-git> 
----------
How to compare files from two different branches?
```git
git diff mybranch master -- myfile.cs
```
From <https://stackoverflow.com/questions/4099742/how-to-compare-files-from-two-different-branches> 
----------
Git merge without auto commit
git merge <branch> --no-commit

Or: 

git merge <branch> --no-commit --no-ff
FF: fast forward
From <https://stackoverflow.com/questions/8640887/git-merge-without-auto-commit> 
-----------
Undo a Git merge that hasn't been pushed yet
git reset --hard HEAD~1
From <https://stackoverflow.com/questions/2389361/undo-a-git-merge-that-hasnt-been-pushed-yet> 
----------------
Git to omit deleted files.
git diff --diff-filter=d
From <https://stackoverflow.com/questions/3692152/suppressing-diffs-for-deleted-files-in-git> 
----------------
Remove untracked files:
//if you want to decide
git clean -di
//get rid of everything
git clean -df
From <https://www.hacksparrow.com/git/remove-untracked-files-and-directories.html> 
-----------------


How to squash with respect to the master:
git rebase -i master
From <https://stackoverflow.com/questions/25356810/git-how-to-squash-all-commits-on-branch> 

Then follow the instruction. 
Change Pick to squash.
And the change your comment to whatever you desire.

git push --force origin my_branch
From <https://stackoverflow.com/questions/5667884/how-to-squash-commits-in-git-after-they-have-been-pushed> 


Git  merge conflict:
Use this option
-X theirs

------------------------------------------------------
Destroy your local changes (anything that's not pushed)

	Ø git fetch
	Ø git reset --hard origin/master

From <https://stackoverflow.com/questions/2452226/master-branch-and-origin-master-have-diverged-how-to-undiverge-branches/2452610> 

----------------------
Amending commits:
Amend changes the commit hash
	Ø git add
	Ø git commit --amend

-----------------------------------------------
Force pushing is required to update branches already pushed to the server (but it hasn’t been merged into integration) you will need to force push rebases, squashes, and amended commits since the commit hashes have changed.

	Ø git push -f
-------------------

Steps to Squashing a merged branch:

> git checkout feature/my-branch
> git checkout feature/my-branch
> git checkout -b feature/my-branch origin/integration
> git merge --squash feature/my-branch-orig
> git commit -m “MBE-1234: My feature”
> git push -f origin feature/my-branch



-----------------------------
Squashing 2 past commits together:
git rebase --interactive HEAD~2
Follow the rest as if it was any other squash. 
-------------------
