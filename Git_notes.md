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
