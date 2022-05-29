# cheatsheet for git

### name and email address configuration

    git config --global user.name "Your Name"
    git config --global user.email you@example.com

### sign commits with GPG

    git config --global commit.gpgsign true
    git config --global user.signingkey B5C9.......
    git config --global alias.logs "log --show-signature"

### set default branch

    git config --global init.defaultBranch main

### Move, transfer the most recent commit(s) to a new branch with Git

**Moving to an existing branch**

If you want to move your commits to an existing branch, it will look like this:

    git checkout existingbranch
    git merge master
    git checkout master
    git reset --hard HEAD~3 # Go back 3 commits. You *will* lose uncommitted work.
    git checkout existingbranch

You can store uncommitted edits to your stash before doing this, using git stash. Once complete, you can retrieve the stashed uncommitted edits with git stash pop.

**Moving to a new branch**

**WARNING:** This method works because you are creating a new branch with the first command: git branch newbranch. If you want to move commits to an **existing branch** you need to merge your changes into the existing branch before executing git reset --hard HEAD~3 (**see Moving to an existing branch above**). **If you don't merge your changes first, they will be lost.**

Unless there are other circumstances involved, this can be easily done by branching and rolling back.

    # Note: Any changes not committed will be lost.
    git branch newbranch      # Create a new branch, saving the desired commits
    git checkout master       # checkout master, this is the place you want to go back
    git reset --hard HEAD~3   # Move master back by 3 commits (Make sure you know how many commits you need to go back)
    git checkout newbranch    # Go to the new branch that still has the desired commits

But do make sure how many commits to go back. Alternatively, you can instead of HEAD~3, simply provide the hash of the commit (or the reference like origin/master) you want to "revert back to" on the master (/current) branch, e.g:

    git reset --hard a1b2c3d4

*1 You will only be "losing" commits from the master branch, but don't worry, you'll have those commits in newbranch!

**WARNING:** With Git version 2.0 and later, if you later git rebase the new branch upon the original (master) branch, you may need an explicit --no-fork-point option during the rebase to avoid losing the carried-over commits. Having branch.autosetuprebase always set makes this more likely. See John Mellor's answer for details.

### undo local commit

This will undo your latest (1) local commit (undo previous `git add` and `git commit`).

    git reset HEAD~1
    
Now you can change the files, and do `git add` and `git commit` again.

### revert last number of commits

    git revert --no-commit HEAD~5..
