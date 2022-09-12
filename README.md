# reduce-repo-size
Delete all the previous commits

# CAREFUL - This will delete all your previous commits, you will no longer be able to access the previous commits.

So keep a backup of your repository `git clone https://github.com/USERNAME/REPOSITORY.git`

### Recommended
Use this, only if you have just one branch, for multiple branches goto the second method


Deleting the `.git` folder may cause problems in our git repository. If we want to delete all of our commits history, but keep the code in its current state, try this:

```
# Check out to a temporary branch:
git checkout --orphan TEMP_BRANCH

# Add all the files:
git add -A

# Commit the changes:
git commit -am "Initial commit"

# Delete the old branch:
## (Here we used "main", assuming we have just one branch)
git branch -D main

# Rename the temporary branch to main:
git branch -m main

# Finally, force update to our repository:
git push -f origin main
```


### Universal Method

```
# Clone the project, using he following command:
git clone https://github.com/USERNAME/REPOSITORY.git

# Change Directory to your REPOSITORY:
cd REPOSITORY

# Delete the `.git` folder, this contains all the previous commits:
git rm -rf .git

# Initialize the repository:
git init
git remote add origin https://github.com/USERNAME/REPOSITORY.git
git remote -v

# Add all the files and commit the changes:
git add --all
git commit -am "Initial commit"

# Force push update to the main branch of our project repository:
git push -f origin main
```
