### master
* #cloning the git of exercises
* `git clone https://gitexercises.fracz.com/git/exercises.git`
* `cd exercises`
* #setting up name and email so that
* `git config user.name "Tanmay"`
* `git config user.email "tanmaybothra496@gmail.com"`
* #sets up the game mechanism i.e. git start , git verify and so on
* `./configure.sh`
* `git start`
* `git verify` 
* #says PASSED
* `git start next`

### commit-one-file
* `ls` 
* there is A.txt B.txt README.md start.sh
* `git status`
* #A.txt and B.txt are untracked
* `git add A.txt`
* #adds A.txt in index
* `git commit -m " "`
* `git verify`
* #PASSED
* `git start next`

### commit-one-file-staged
* `git reset HEAD A.txt` 
* #reset only with respect to A.txt
* #now with git status we can see that A.txt is untracked
* `git commit -m ""`
* `git verify`
* `git start next`

### ignore-them
* i created .gitignore file
~~~
*.exe
*.o
libraries/
*.jar
~~~
* added this
* now git status only shows that file.txt and .gitignore are untracked
* `git add .` 
* to add all (i.e. file.txt and .gitignore)
* `git commit -m ""`
* `git verify` `#PASSED`
* `git start next`

### chase-branch
* i discovered there are multiple answers
* `git merge escaped`
* (since the result of the merge result in same state as escaped they have same hash hence they become same)
* this is called fast forward merge
* another way is 
* `git reset escaped`
* (it resets the curent branch to the given branch)
* `git start next`

### merge-conflict
* `git merge another-piece-of-work`
* #it shows merge conflict
* #i opened equation.txt in vim and fixed it
* `git add equation.txt`
* `git merge --continue`
* `git verify`
* `git start next`

### save-your-work
* `git stash`
* then i edited bug.txt
* `git add .`
* `git commit -m "Bug fixed"`
* `git stash pop`
* then i edited bug.txt again added the final line
* `git add .`
* `git commit -m "i did it"`

### change-branch-history
* `git rebase hot-bugfix change-branch-history`
* #rebase : second parameter gets attached to the first one

### git rm ignored.txt
* `git rm ignored.txt`
* then commit

### case-sensitive-filename
* `git mv File.txt file.txt`
* `git commit -m ""`
* `git verify` 

### fix-typo
* `git reset --soft HEAD~1`
* #modified the file
* `git add .`
* `git commit -m "Add Hello world"`

### forge-date
* `git log` 
* #there date appears, i can see the date format
* `git commit --amend --date='Sat Mar 14 16:16:19 1987 +0530'`
* `git verify`

### fix-old-typo
* `git rebase --interactive HEAD~2`
* changed pick to edit for the one that i want to edit
* edited file 
* `git add .`
* `git commit --amend '-S'`
* fixed the title as well
* `git rebase --continue`
* fixed the conflict 
* `git add .`
* `git rebase --continue`
* `git verify`