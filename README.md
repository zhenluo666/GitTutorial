# Git Tutorial
###  Basic Git commands
#### 1. Start with Git
##### --- Clone the repository to your local machine (go to the directory at your local machine)
`git clone https://github.com/zhenluo666/GitTutorial`
##### --- Instead of cloning, you can also creat a new repository at local machine (go to the directory at your local machine)
`git init`  
`git remote add origin https://github.com/zhenluo666/GitTutorial` 
#### 2. Get the status of repository at local
`git status`
#### 3. Include untracked files or update unstaged files at git status check (after you make changes to files in local repository)
##### --- Add/Update a specific file
`git add {filename}`
##### --- Add/Update all files within directory
`git add .`  
`git add *`  
`git add -A`
#### 4. Discard changes to an existed file (restore the file wrt github server version)
`git restore {filename}`
#### 5. Commit the change from staging to local repository (with messages -m)
`git commit -m "updated the README with more commands"`
##### --- Combine add and commit commands (using &&)
`git add . && git commit -m "add more lines"`
##### --- Check the info of commit (commit hash number, author, date, etc.)
`git log`
#### 6. Sync the repository from local to github server (remote)
`git push`  
`git push -u origin main`  
`git push origin {new_remote_branch}`
#### 7. Sync the repository from github server (remote) to local
##### --- Retrieve/Fetch remote-tracking branches (After fetch, you can merge the received commits into local branch using git merge)
`git fetch`  
`git fetch {remote_repository} {remote_branch}`
##### --- Retrieve and merge from remote (git pull = git fetch + git merge)
`git pull`  
`git pull origin {remote_branch}:{local_branch}`  
`git pull {remote_repository} {remote_branch}:{local_branch}`  
`git checkout -b {new_local_branch} origin/{remote_branch}`  
% Note pull may create merge conflict between remote and local that you need to be fix and commit the change
#### 8. Editing in git config (exit only; exit w/o saving; exit w/ saving)
`:q`  
`:q!`  
`:wq`  
#### 9. Edit git configuration file (author and email)
`git config --global --edit`
#### 10. Help
`git --help`
#### 11. Remove files from staging area (undo the git add)
`git reset {filename}`
#### 12. Undo the git commit at local repository
`git reset --hard origin/{branch_name}`
#### 13. View infomation about the remote repository
`git remote -v`  
`git branch -a`
#### 14. Obtain the difference between branches
`git diff {main_branch} {new_branch}`

### Branches
#### 1. Make branches (avoid messing up with main/master branch and able to merge later)
`git branch {new_branch}`  
`git branch {new_branch} {base_branch}`  
`git branch {new_local_branch} {remote_repository}/{remote_branch}`  
`git checkout -b {new_branch}`  
`git checkout -b {new_local_branch} origin/{remote_branch}`  
#### 2. Switch to a specific branch (commit changes before switch)
`git checkout {branch_name}`
#### 3. Branch operation
`git branch --list`  
`git branch -D {branch_to_be_deleted}`  
`git branch -M {branch_to_be renamed}`  
`git branch -C {branch_to_be_copied}`  
`git push origin --delete {remote_branch_to_be_deleted}`
#### 4. Merge branch (merge a specific branch/commit to current branch)
`git merge {branch_name}`  
`git fetch origin {remote_branch} && git merge origin/{remote_branch}`  
`git fetch {remote_repository} {remote_branch} && git merge {remote_repository}/{remote_branch}`  
% There may be merge conflict which needs your check into files and make modifications  
% Merge conflict has to be resolved before switch branch

