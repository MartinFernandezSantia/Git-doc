# Introduction to Git

[Video explaining basic Git stuff](https://www.youtube.com/watch?v=9uGS1ak_FGg)

### Git commands to start new repository:

Inside a folder.

- **git innit**
- **git add .**
- **git commit -m "Your message"**

---

### Git commands to connect to remote repository

- **git remote add origin https://github.com/YourName/YourRepositoy**
- **git push -u origin main**

---

### Create pull requests:

This is used when we want to request the one with permissions to push our changes into the original repo.
-**git request-pull -p origin/main**

---

### Complete pull request

As the owner of the repository where the pull request was done by another user, this are the steps to add the changes to the main brach:

- **git remote add `name` `URL`** _It's important to set up the repo of another dev as a remote when you want to incorporate their changes into your project_
- **git pull `remote_name` `branch_name`** *In this case the `remote_name` is the name of remote repo we set up before, and the brach name could be `main`*

---

### Work with braches

- **git branch `branch_name`** _Create a new brach of current branch (usually `main`)_
- **git checkout `branch_name`** _Switch to new branch_
- Or use **git checkout -b `branch_name`** to create and switch to the new branch
- **git merge --ff-only `branch_name`** _This is done when we want to fast-forward merge the changes in a branch, back to the `main` branch (must be done from `main` branch). `--ff-only` is not a must but a good practice since it will fail if `main` has changed_

---

### Resolve merge conflicts

There are a few options to deal with this:
1.

- Run the **git merge --abort** command to restore the `main` branch to what it was before the attempted merge
- Run **git pull** to ensure you have the latest changes.
- Create a new branch, make your changes, and merge back into the main brach.
- Push changes
2. 
- Run the **git reset --hard** command to get back to how the repo was before you started the merge.

3.

- Resolve the conflict manually by using information that Git inserts into the affected files.
- Then use **git add** to tell Git that the conflict has been resolved
- After that, commit the changes.
- Lastly, push the changes to the main branch.

---

### Git commands

- **git init** _Initializes git repository in current folder_

-**git init --bare** _Initializes a bare repo which doesn't have a working tree. It's used when working with many peope, so that everybody can push changes without worrying about which branch is checked out _

-**git symbolic-ref HEAD refs/heads/main** _Used instead of `git checkout` when using a bare repo that's still bare _

- **git status** _Shows the status of changes as untracked, modified, or staged_

- **git add -A** _Stages all changes but only for files that are already being tracked_

- **git add .** _Stages all changes, but it only stages modifications and new files. It does not stage deletions_

- **git commit -a** _Stages and commits all changes, for tracked files_

- **git commit -m "Message"** _Commits changes and allows to add a message_

- **git commit index.html -m ""** _Same as before but only commits the changes of the index.html file_

- **git commit -am ""** _Shorthand way of doing "git add -A" and "git commit -m"_

- **git commit --amend --no-edit** _Amend small changes to last commit instead of creating a new one, and don't change the message_

- **git checkout 8e19143 .** _Reverts to commit with specific hash and brings everything from it_

- **git checkout -- index.html** _If we deleted index.html from our working directory but still have it in our last commit, this is how to recover just that file_

- **git diff** _This shows the differences between our las commit and our current directory_

- **git log --oneline** _The --oneline is optional, it simplifies the log shown_

- **git rm index.html** _Stop tracking index.html in all commits_

- **git reset HEAD index.html** _Recover index.html in our commits after "git rm index.html"_

- **git reset --hard HEAD^** _Goes back to the commit before our last commit, and deletes all commits after that_

- **git stash** _Saves the state of the working tree and index by making a couple temporary commits._

- **git stash pop** _Used to merge the chages_

- **git branch `branch_name`** _Create a new branch_

- **git checkout -b `branch_name`** _Create the branch and switch to it_

- **git branch --show-current** _Show current working branch_

- **git branch -a** _To show all branches_

- **git merge --ff-only `branch_name`** _Merge branch into `main` branch by performing a fast-forward merge, which is considered a good practice_

- **git merge `branch_name` --no-edit** _Used when we want to merge a branch into main but we know main has changed_

---

### Git related files

- **.gitignore** _Inside this file we'll write the names of all files or file types that we don't want git to keep track of_
- **.git-keep** _Empty file which goes inside empty folders we want git to keep track_
