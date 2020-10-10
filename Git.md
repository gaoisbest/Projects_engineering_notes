# 0. New a branch and change to this branch
`git checkout -b platform`


# 1. Unstage added files
```
# already git add a.py
git add a.py

# undo git add operation
# git status give the clue
git reset HEAD a.py
# undo all added files
git reset HEAD .
```
# 2. Update user name
```
# look at current name
git config user.name
git config user.email

# update current project's user name and email
git config user.name new_name
git config user.email new_email

# update global user name and email
git config --global user.name new_name
git config --global user.email new_email
```

# 3. Remove git attribute for a folder
```
# from https://stackoverflow.com/questions/4754152/how-do-i-remove-git-tracking-from-a-project
rm -rf .git
```

# 4. In local, go back to history version, and push to server
```
# go back to history version
git reset --hard commit_id

# push to server
git push origin branch_name --force
```

# 5. [change to specific tag](https://stackoverflow.com/questions/791959/download-a-specific-tag-with-git)
```
# show all tags
git tag -l

# checkout tag
git checkout tags/tag_id

# checkout tag and new branch
git checkout tags/tag_id -b new_branch_name
```
