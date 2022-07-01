This is macbook part 

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

