# git-cheatshit

## Pull 
`git pull origin <branch-name>` 
## Push
### Push arguments
`git push <remote> <place>` Specifies where the commits are coming from and where they are going. No need for the current branch.   
`git push origin <source>:<destination>` = refspec. Specifies the source of the commits and their destination. Creates the destination branch if it doesn't exist.   
*Example*: `git push origin main^:side` the commits of main^ will be added to the remote branch side.  
## Fetch
### Fetch arguments
`git fetch origin <place>` Goes to the remote branch place, retrieves the not present local commits and copies them in the local branch origin/place.    
## Branches 
### Add/Create
`git fetch origin  :<branch-name>` Creates the branch in the local repository. The left side of the refspec was left empty.   

## Remote branches
### Delete 
`git push origin  :<branch-name>` Deletes the branch in the remote repository. The left side of the refspec was left empty.   

### Remote tracking  
`git checkout -b <new-branch> origin/main` Creates a new branch, checkout on it and defines main as the tracked branch.   
`git branch -u origin/<trackedBranch> <branch-name>` Makes an existing branck track origin/trackedBranch.  
git`git branch -u origin/<trackedBranch>` Makes the current branch track origin/trackedBranch.


