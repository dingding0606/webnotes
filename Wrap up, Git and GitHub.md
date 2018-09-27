# Wrap up, Git and GitHub

### To create a website, we usually consider three different parts:

-   **Client-side**
    -   JS
    -   HTML
    -   CSS
-   **Server-side**
    -   Python
    -   JS
    -   PHP
    -   Ruby
-   **Database**
    -   SQL
    -   NOSQL

Heroku: Make your own website on the internet

Github page: Only for static page, nothing about server-side



### Git Commands

```bash
git init
# initialize git repository


git add <filename>
git add --all
git add .
# tell git that a newly created file should be included in the next "commit"


git commit -m "Created hello.py"
# save a snapshot of the current version of the code; include a human readable message


git log --oneline
# view the commit history


git status
# view the current state of the repostitory, show modified, staged, and untracked files


git branch <branchname>
# create a branch called <branchname>
git branch
# show a list of all the branchs


git checkout <branchname>
# switch to <branchname>


git reset <hash-name> 
git reset <hash-name> --hard
# returns code to a previous state; Careful, can not be undone!
git checkout <hash-name>
# view the state of a repository at a particular status


git merge <branchname>
# while merging, I have to checkout to destiantion first, then merge the branch


git remote add <REMOTENAME> <link of repository>
git remote show <REMOTENAME>
git remote show origin
# manage remote repositories; origin is the convention


git push <REMOTENAME> <BRANCHNAME> 
git push origin master
# update remote repository with any commits made locally; origin is the convention
git push -u <REMOTENAME> <BRANCHNAME> 
git push
# shortcut: when the first time that push to the repository, use -u; next time, simply use git push as a shortcut


git pull: update local repository with any changes made remotely
```

Convention of Git branches:

-   master

-   develop