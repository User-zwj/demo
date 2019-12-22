# demo
Demo of using GitHub

### When you create a branch test_branch locally, make some changes on this new branch. Then you need create test_branch remotely and push the changes remotely

  git push --set-upstream origin test_branch  
  
  or 
  
  git push -u origin test_branch
  
### List local and remote branches
  
  git branch -a                           
  
  git checkout master
  
  git merge test_branch
  
### Remove branch locally
  
  git  branch -d test_branch    
  
### remove branch remotelly
  
  git push origin --delete test_branch   

### rename branch
  
  git branch -m old_name new_name
  
  
## Time machine
### Reset the commit message (1st: change the most recent one; 2nd: reset actions for the recent 3 commits)

  git commit --amend
  
  git rebase HEAD~3 -i
  
### Reset working tree (before git add) (1st: clear all changes made on file_name; 2d: clear all changes made after last commit)

  git checkout -f file_name
  
  git checkout .
  
### Reset staging area (after git add) (the file_name will become unstaged)

  git reset HEAD file_name
  
### Regret after you made commit locally (all changes will become unstaged)

   git reset HEAD~1
   
### git checkout VS git reset VS git revert 
#### (The following two work the same, 2 in the second one can be changed depending on which commit you wanna checkout) This only allows you to see what it looks like several steps ago and will not affect your commit history. To get back where you are initially, use 'git checkout master'

   git checkout 8-digit-SHA
   
   git checkout HEAD~2
   
 #### The following two work the same. This will get back to the version 1 step earlier, and all the changes you made after previous commit are unstaged now. You can make edit now, but when you want to push to the remote, you will need to use 'git push -f origin master' to force push
 
   git reset HEAD~1
   
   git reset 8-digit-SHA
   
 #### The only difference of the following two is that this will drop all the changes made after previous commit 
 
   git reset --hard HEAD~1
   
   git reset --hard 8-digit-SHA
   
 #### This one is the most recommended if you regret. It only the corresponding commit and all the others will keep the same. And it will make a git commit and you will not need force push in the end
 
   git revert HEAD~1
   
   git revert 8-digit-SHA
  
  

