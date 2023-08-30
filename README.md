# Demo

I am Learning Github Using Youtube.
Good.


# ls -la :  
shows hidden folders

# git status :
 shows those files that are modififed, updated created or deleted but havent saved

# git add or git .add

1: .means add/include all untracked files. You could also tell names of the each file


# git commit: files ready to commit
# git commit -m "Message"

m: means message
"" : add message meaning or meaningless
# git commit -m "Message" -m "Discription"

-m: another message as Discription 

# till now Data is saved Locally

# generating SSH key
1: ssh-keygen -t rsa -b 4096 -C "emial.com"
2: give name for the key
3(check key) : ls | grep keyname
4 : upload .pub file .pub = public
put on github
5 : extention with .out is private key for only you.
use private key that you generated that public key
6 : cat keyname.pub -> will show key 
7 :  copy it pbcopy < ~/keyname.pub

# git push origin (branch name)
1: origin -> option set for location to get our repository
2: I am chcking if this works or not
3: I am checking again 


# Workflows
# Github: 
    write code -> Commit change -> Make a pull request

# Local Git:
    write code -> Stage Changes(git add .) -> Commit Change(git commit -m "") -> push change(git push origin main) -> Make a pull request. 



# Extras
1. git push origin main
2. git remote set-url origin "url"
3. ssh-add ~/.ssh/keyname
3.ii ssh -T git@github.com
4. git remote -v


# Branches
 main Branch is Default Branch

...Another Branch or Feature Branch
...If you made commit to F branch you will see only changing them into feauture branch
...but if you switch to main branch you wont see any changes of feauture branch
...Each branch keeping change of its own data
...working on feauture branch for weeks
...But there will be a bug that you have to fix using 
...Hotfix Branch

# Creating a new branch

git checkout -b nameofbranch-description-description

git merge : to merge two branches code
git diff : what difference has made


# PR or  Pull Request

pulling Request to pull data/code to another branch

making pull requesst from main branch to new branch

# Steps of PR:
1.Link given after pushing code to new Branch.

2.Using Github

Use : when somebody addedd code to new branch you inspect it and then merge it with your main branch
i.Open Pull Request section on github from <>code
ii.Enter Name, Enter Desc
iii.You can add comment on code of lines
iv. Merge Pull Request


after this code on vs code wont change becuse we used github
to change code on vs code main branch also, we have to import/update it

v. Git pull origin main
or
git pull
only if upstream is on

then Delete other new branch because now we dont need that.

git branch -d newbranchname


# merge conflict 

when multiple people are using same branch, there may be conflict
1. Del previous branch
2 create new branch