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