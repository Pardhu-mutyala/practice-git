Practice - git == Beginner friendly

we can create a new branch by using below command

git branch <branch-name>

git checkout -b <branch name> # ir will create a new branch and switch to it the new branch.

We can check the commit history using gir log command

logs: git log  



once after raise the pull request the reviewer can see the changes and suggest the recommended things if needed, or else they directly approved it.

once got the approval from the reviwer we can merge it the main branh.

to see the print log file
git cat-file p

Merge vs rebase

1. Merge creates extra commit and rebase does't create a merge commit 

2. Merge preserves the history, Rebase does not preserve the history

3. Rebase the rewrites the history, it will change commit id.

4. Rebase has linear history, Merge is in circular history

If a branch is shared among multiple members, wants to preserve the history---> Use Merge

have less members and less collab ---> use rebase

Mergr conflicts:
when two are more developers working on a same file and made changes simulataneously.
when try to merge those changes and it becomes conflicts because git does't which file changes needs to keep in it.
So git raise merge conflicts. so we need to resolce them and later push it again and merge it.
