There are three stages in git - > working tree , staging area and git directory. 

- Working tree represents the place where we are making changes to our file
- We can use **git status** ,what all are things that are included inside the working tree
- To add files in working tree , we use **git add FILENAME**
- To commit we use either **git commit** , Here it will open text editor to write commit messages 
- Or you can use the short cut **git commit -m "YOUR MESSAGE"**  

To add any file working 

We cannot commit without any commit message

If you are working in a previously added files in git repo , then after doing the edits , we can directly say **git commit -a -m "message"**

Here the -a flag will automatic add the changes to the staging area and commit 

-> Remember this wont work for the new files that are added newly

when you use **git log** we obeserve various commit id and their messages ,

There you can also see the head pointer 

Git Uses the Head alias to represent the currently checked-out snapshot of the project

- the git log command only shows the the id , and message , but if we want to see the changes in the commits too then , we need used -p flag as **git log -p**
- you can use the **git show ID** to get the information of the particular commit
- If you want to see the number of lines changed then **git log --stat**

- so if you want to see the what are all the differences in the file form the previous files the we use **git diff** command , it will show you all the changes that are happend in the current non staged area with respect to the previous commit . 
- If you want to see the differences on in one file , the pass its name as its parameter like: **git diff NAME**
- so when we are done with our edits , and perparing to go for the staging are , if we want to look for all the edits that has been done uptil now then we can use **git add -p** this will show the changes that been made , will ask will you want to go to staging area or not.
- so if we want to see the changes that has been made and staged also then we use the command **git diff --stage**

Deleting and renaming 

- git rm filename
- git mv pastName presentName

Telling git to ignore some files , we use .gitignore file

## Week 2

Here there is one method "checkout" is used to undo the changes in the file that are not added{Stage}. 

*git checkout filename* 	this will undo all the changes 

If you want to reset the added files. then we use 	*git reset HEAD FILENAME*

### Amending the previous commit

Here while doing the commit we have made some mistake. Then in that case, we have the option to over write the resent commit by using **git commit --ammend** Avoid amending commits for public repo

### Roll backing the commits

Here we can  actually undo all the changes in the commit and added as a new commit 

If you want to roll back the latest commit use -. **git revert HEAD** 

and if you want to roll back any particular commit then -> **git revert COMMITID*

### Git branches and Merge Conflicts

Here to introduce the branch we use **git branch BRNACHNAME**

to go into that branch we use **git checkout branchname**

Here is we want to create new branch and move to it then use : **git checkout -b BRANCHNAME**

---

if you want to merge the branches then go to parent branch , then use git merge BRANCHNAME

| git branch                | used to see the branch        |
| ------------------------- | ----------------------------- |
| git brach NAME            | to create a new branch        |
| git branch -d NAME        | to delete the branch          |
| git branch -D NAME        | forcibly deletes the branch   |
| git checkout BNAME        |                               |
| git checkout -b BNAME     |                               |
| git merge master          |                               |
| git log --graph-- oneline |                               |
| git branch -r             | to look for the remote branch |

to merge any branch into branch2, first we want to go that branch and latter  use git merge branch2

shortcut -> git merge branch main

## Week 3

to save the credentials we can use the credential helper =>**git config --global credential.helper cache**

This will store the password

Here the remote repo is named origin by default

**git fetch fetches the remote updates but doesnt merge , git pull fetches the remote update and merges .**

so if there is merge conflicts in the our local with the remote , we can use the git fetch and the manually merge that

if we want to update all the remote branches locally without merging with the local branches then , we can call **git remote update**

| Command              | Explanation & Links                                          |
| :------------------- | :----------------------------------------------------------- |
| git remote           | [Lists remote repos](https://git-scm.com/docs/git-remote)    |
| git remote -v        | [List remote repos verbosely](https://git-scm.com/docs/git-remote#Documentation/git-remote.txt--v) |
| git remote show NAME | [Describes a single remote repo](https://git-scm.com/docs/git-remote#Documentation/git-remote.txt-emshowem) |
| git remote update    | [Fetches the most up-to-date objects](https://git-scm.com/docs/git-remote#Documentation/git-remote.txt-emupdateem) |
| git fetch            | [Downloads specific objects](https://git-scm.com/docs/git-fetch) |
| git branch -r        | [Lists remote branches](https://git-scm.com/docs/git-branch#Documentation/git-branch.txt--r); can be combined with other branch arguments to manage remote branches |

If we want to push a local branch to the remote repository then we can use this command 

**git push -u origin BRANCH**

Here origin is refer to the remote repo, -u => refer to upstream, the Branch is the name of the local branch

## Git merge

Merging refers to add changes from other branches to my current branch , Here if we want to add changes of BRANCH1 to BRANCH2

the first we got to branch2 , then we merge  changes of BRANCH1

```bash
git checkout BRANCH2
# now i am inside the BRANCH2 , then i will merge changes of BRNACH1 to my current BRANCH
git merge BRANCH1
```

 

Note: if you are working in a feature branch always try to merge changes of main to feature , so that when you finally added the feature branch to main , there are less conflicts 



## Git Rebase

git rebase is alternate of git merge , Rebasing instead of merging rewrites history and maintain linear commits , making code history clean.

Here is what git Merge is :

![image-20220711232026921](/home/tushar/.config/Typora/typora-user-images/image-20220711232026921.png)

 

Here is what git rebase is:

![image-20220711232128062](/home/tushar/.config/Typora/typora-user-images/image-20220711232128062.png)



As you can see , the git rebase actually move the whole feature branch and moved in front of main branch , this leads like a single linera commit history  
