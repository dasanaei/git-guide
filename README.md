# Git Guide

## Start a project
To start a project, you have two options. Either create a new repository or download (clone) an existing repository on Github.
### From a repository
Begin by navigating to the repository on Github.com. Press the "Clone or Download" button, and copy the HTTP link of the repository. 

Then open a terminal windows and cd to a location you want to download the project. Once at the desired location, run the following command. 
```
git clone [HTTP Link of Repository]
```

### New 
Go to the Github.com and login. Press the "+" button in the top right corner, and select "new repository". Fill in any prompted information required (like a name/description)

Once a new repository has been created, create a folder in your computer and cd to that location from the terminal. Begin to create your files and write a little code (or a readme). Once ready to upload your first changes, run the following commands:
```
git init
git add .
git commit -m "first commit"
git remote add origin [HTTP Link of Repository]
git push origin master
```

## Create a new branch
Branches allow multiple version of the project to exist at once. They are very useful when more than one person is working on a project, or when you are creating a new addition and do not want to poison the main code with untested changes. 

Every project begins with a master branch. To make more run the following
```
git checkout -b "Branch Name"
```
This will create a new branch. You can see this branch on Github in the branch dropdown menu. Once done with some additions push changes.

To switch branches (ie. return to master branch to get new additions), run the follwing
```
git checkout "Target Branch"
```
## Push changes
Pushing to a repository means to uplaod the code you worked on. It consists of 3 steps. First you must add all files, so it knows that changes have been made. Then you must make a commit, this is a message that can be seen on the website that easilly allows for users to understand what the changes were. Then you must run the push command.

When you are ready to upload your changes run the following
```
git add . 
git commit -m 'Commit Message'
git push origin [Insert branch name]
```

It is vital to specify the branch name you were working on. Never push directly to master unless at the beginning of a project
## Pull changes

Pulling from a repo means to download changes that have been made. This should be done if you want to update your code to match what is on the repository. 
```
git pull origin [Branch]
```

## Rebase 

This is a complex step required before merging. Rebasing allows the user to update their branch with additions to the branch they are going to merge to. For example if I was working on a feature on my own branch called "feature1", and during this time several people pushed changes to the master branch, I can no longer easilly merge. First I must rebase my code. Begin by,
```
git fetch origin 
git rebase origin/master
```
At this point, there usually are errors in the merge. Use `code .` to open vscode and manually see where the errors are. In the file tree, all files marked with a colored "C" mean there was an error. Scroll through the file to fix it. Once all errors are cleared, run
```
git rebase --continue
```
If all errors are cleared, and the rebase is successful, then run
```
git add .
git push origin [branch]
```

## Merge
Merging with the master should be done entirelly on the website. Go to the repository and enter the pull request tab. There choose the branch you are merging and the target branch you want to merge to. The merge request should be checked over by another person and merged with a comment. 