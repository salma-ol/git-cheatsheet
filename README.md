# git-cheatsheet
## Set up 
`git config --global user.name "John Doe"`      
`git config --global user.email johndoe@example.com`     
`git config --global user.password password`
`git config --global core.editor "code --wait"` Changes git's editor to vscode   
Create a new repository on the command line
```
echo "# git-test" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin <url>
git push -u origin main
```
## Status 
`git status` Checks the status of ur files    
`git status -s` Returns a more compact status    
## Unstaged files
`git diff` Checks unstaged/cached files    
`git add <file name>` Stage the file     
`git add .` Stage all the unstaged files    
## Commits 
`git log` Viewing commit history  
`git commit --amend` Change the log message or the files that appear in the last commit.    
### Move commits 
`git checkout <commit-hash>` Detachs the HEAD if its done on the most recent commit otherwise it moves HEAD to the named commit hash       
`git checkout <commit-hash>^` Moves the HEAD one commit upwards     
`git checkout <commit-hash>~<num>` Moves the HEAD num commits upwards    
## Pull 
`git pull origin <branch-name>` Downloads the not present commits from the remote branch and merges them with our current HEAD.    
`git pull origin <source>:<destination>` Downloads the not present commits from the remote branch source and merges them with our current HEAD. Creates the destination branch if it doesn't exist.    
`git push --set-upstream origin <branch-name>` Pushes to the remote repo to a remote branch that wasn't created. A verifier !!!!!    
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
`git branch <branch-name>` Creates a new branch    
`git checkout <branch-name>` Switchs to the indicated branch    
`git checkout -b <branch-name>` Creates and checkouts to the indicated branch    
`git checkout -` Returns to the previous checked-out branch (works with commits too)     
`git fetch origin  :<branch-name>` Creates the branch in the local repository. The left side of the refspec was left empty.   
### Merge
`git merge <branch-name>` Merges the branch to current checked-out branch    
### Rebase 
`git rebase <branch-name>` Merges the current checked-out branch to the branch ?? a verifier en pratique c 'est comme merge
### Branch forcing 
`git branch -f <branch-name> HEAD~<num> | git branch -f <branch-name> <commit-hash>` Force the reassignment of branch-name to a commit.     
## Remote branches
### Delete 
`git push origin  :<branch-name>` Deletes the branch in the remote repository. The left side of the refspec was left empty.   
### Remote tracking  
`git checkout -b <new-branch> origin/main` Creates a new branch, checkout on it and defines main as the tracked branch.   
`git branch -u origin/<trackedBranch> <branch-name>` Makes an existing branck track origin/trackedBranch.   
`git branch -u origin/<trackedBranch>` Makes the current branch track origin/trackedBranch.    
## Reversing changes 
### Reset 
Rewrites history. Moves a branch backwards as if the commit had never happened. The changes can't be shared on the remote branch.     
`git reset <commit-hash>|HEAD~<num>` Moves the checked out branch to the referenced commit. 
### Revert
Reverse changes that can be shared.     
`git revert <commit-hash>|HEAD` Reverses the changes made in the referenced commit. Created another commit. 
## Moving work around  
### Cherry-pick
`git cherry-pick <commit1> <commit2> <...>` Copy a series of commits below your current location.     
### Interactive rebase
`git rebase -i <commit-hash>|HEAD~<num>` Reorder, drop, squash, amend, ... the commit below the referenced commit.    
## Git tag
`git tag <name-tag> <commit-hash> -m "message"` Tags the referenced commit. 
## Git describe 
`git describe <ref>`    
Output: `<tag>_<numCommits>_g<hash>`     
tag -> closest ancestor tag in history.     
numCommits -> how manny commits away that tag is.     
hash -> the hash of the commit being described.   




