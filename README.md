# Introduction to Git

[Video explaining basic Git stuff](https://www.youtube.com/watch?v=9uGS1ak_FGg)

### Git commands to start new repository:

Inside a folder

- **git innit**
- **git add .**
- **git commit -m "Your message"**

### Git commands to connect to remote repository

- **git remote add origin https://github.com/YourName/YourRepositoy**
- **git push -u origin main**

### Git commands

- **git init** _Initializes git repository in current folder_

- **git status** _Shows the status of changes as untracked, modified, or staged_
- **git add -A** _Stages all changes but only for files that are already being tracked_
- **git add .** _Stages all changes, but it only stages modifications and new files. It does not stage deletions_
- **git commit -a** _Stages and commits all changes, for tracked files_
- **git commit -m "Message"** _Commits changes and allows to add a message_
- **git commit index.html -m ""** _Same as before but only commits the changes of the index.html file_
- **git commit -am ""** _Shorthand way of doing git add -A and git commit -m_
- **git diff** _This shows the differences between our las commit and our current directory_
- **git log --oneline** _The --oneline is optional, it simplifies the log shown_

### Git related files

- **.gitignore** _Inside this file we'll write the names of all files or file types that we don't want git to keep track of_
- **.git-keep** _Empty file which goes inside empty folders we want git to keep track_
