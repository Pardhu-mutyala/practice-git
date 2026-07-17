Practice - git == Beginner friendly

we can create a new branch by using below command

git branch <branch-name>

git checkout -b <branch name> # ir will create a new branch and switch to it the new branch.

We can check the commit history using gir log command

logs: git log  



once after raise the pull request the reviewer can see the changes and suggest the recommended things if needed, or else they directly approved it.

once got the approval from the reviwer we can merge it the main branh.

to see the print log file


git cat-file p <id>


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


Branching Strategy
==================
what are the branches
how you bring changes from DEV to PROD
other branches to main/master branch

git flow -> master develop release feature and hotfix --> waterfall
feature branch --> main merge --> agile devops microservices
trunk based --> main branch

what are the long lived branches
what are short lived branches

longlived branches --> master develop
short lived branches --> feature release and hotfix

main/master --> PROD

develop --> active developments going on
========
source: main/master
destination: main/master

short-lived branches
=====================

feature-1
========
source: develop
destination: develop

clone --> build --> unit test cases --> scan --> create image --> push image --> deploy into DEV

successfully merge into master

feature-2 --> until you merge to develop
=========
1. pull the changes from develop
2. merge/rebase
3. raise PR and merge to develop

Release = New features + Bug fixes + improvements

Release branch --> release-1.3
===============
source: develop
destination: master and develop
lifetime is until that release is successfully sent to PROD. You get the changes to master/main

deploy into environments DEV, QA, UAT and test the application
deploy to PROD. If successfully deployed then you merge these changes into master/main and develop

you can delete release branch when it is successfully deployed into PROD.

waterfall model

product based has to support multiple versions at a time --> 20, 19, 18, 17

git checkout release-18

hotfix
=======
SLA --> Service Level Agreement
priority-1 --> max 4 hours --> business is getting affected

source: main
destination: develop and main

hotfix-emergency-ticket-price --> approval from chairman/CEO

test in develop once and then deploy to PROD. you need to get changes into main and develop both

featuring branching strategy

master/main and feature
========================
web applications will not have versions

feature -->

clone --> build --> unit test cases --> scan --> create image --> push image

merge to main --> DEV, QA, UAT, SIT, PROD

main --> hotfix --> deploy to DEV -> merge the changes to main -> deploy to PROD

change request

Microservices
==============
f-1

git stash --> pause the develop

git checkout main
git pull origin main

git checkout -b h1
few commits
deploy to dev

merge to main --> deploy to PROD

git merge main (local laptop)

githb.pardhu72 --> it is in our servers

git reset
git revert
git squash
git stash
git cherry-pick

git reset/revert -> undo the changes you already commited

reset --> undo the changes before you commit to remote

soft mixed hard

soft --> when you do soft reset, you get the changes into staging area
mixed (default) --> deletes from local commit, staging area and keep it in workspace
hard --> deletes from local commit, staging, working area

if changes are already into remote branches

revert the changes --> but it will not delete anything, it will add the changes as new commit on top reverted commit

1 feature -> 1 commit

if a single person on one branch, you can squash the multiple commits into single commit.
git squash == git rebase -i
not recommended to do in shared branches

git stash
=========
when you are working on something in new feature branch, you got an emergency defect. We need to create hotfix branch immidiately and do the changes
git stash --> save the changes into some temp without commiting
git stash pop --> get the changes from temp area to workspace

git cherry-pick
==============
I am developing feature, but I found some parts of the feature already developed in another branch,

