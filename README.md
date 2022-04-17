# github-cheat-sheet
Commands I use to manage my local and remote github repos.  Run these at the Windows Terminal command prompt. 

Initial Cone of repository created on git-hub.  From https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository
1. Get URL of on-line  repository found under the Code menu on the GitHub home page. 
2. At Terminal prompt: git clone [url]

To push changes to git
* git add --all
* git commit .
* git push origin main
* to force over-write changes to main branch: git push origin main

To pull changes from git. 
* git status -v // tells you what branch you are on.
* git pull origin main
* git merge main


Now and then, you may end up with commits in your commit history that make your local repository too large to push to your remote  Ehren this happens you can follow these steps.

Deleting the .git folder may cause problems in our git repository. If we want to delete all of our commits history, but keep the code in its current state, try this:
Thanks to https://gist.github.com/heiswayi/350e2afda8cece810c0f6116dadbe651

# Check out to a temporary branch:
git checkout --orphan TEMP_BRANCH

# Add all the files:
git add -A

# Commit the changes:
git commit -am "Initial commit"

# Delete the old branch:
git branch -D master

# Rename the temporary branch to master:
git branch -m master

# Finally, force update to our repository:
git push -f origin master
This will not keep our old commits history around. But if this doesn't work, try the next method below.

