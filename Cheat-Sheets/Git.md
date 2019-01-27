


> Written with [StackEdit](https://stackedit.io/).

**Command**|**Description**
:-----:|:-----:
git version|Current installed Git version
Git global options| 
git config --global user.name "<name>"|Define the author name to be used in all repositories.
git config --global user.email <email>|Define the author email to be used in all repositories.
git config --global --list|Provides the user's name and emial and editor
git config --global color.ui true|Change the Git color shecma
git config --global diff.ui auto|Change the Git color schema
git push origin master|Use git push to push commits made on your local branch to a remote repository. The git push command takes two arguments: A remote name, for example, origin. A branch name, for example, master.
git clone https://github.com/magkey/github-demo.git|Clone a GitHub repository
Basic commands| 
git init |Create a Git repository in the current folder
git status|View the status of each file in a repository
git add <file>|Stage a file for the next commit
git commit|Commit the staged files with a descriptive message. This version opens Text Mate
git commit -m "descriptive text"|Commit the staged files with a descriptive message. The -m option lets you spedify a commit message on the command line instead of opening a text editor.
git log|View a repository's commit history
git log --oneline|View a repository's commit history in one line
git log --oneline <file>|View only the <file> commit history
Undoing changes| 
git checkout <commit-id>|View previous commit.
git checkout master|Return to the master branch.
git tag -a <tag-name> -m "<description>"|Create an annotated tag commit by applying a new commit.
git revert <commit-id>|Undo the specified commit by applying a new commit.
git reset --hard|Reset tracked files to match the most recent commit.
git clean -f |Remove untracked files.
git reset --hard / git clean -f|Permanently undo uncommitted changes.
Branches, Part I| 
git branch|List all branches.
git branch <branch-name>|Create a new branch using the current working directory as its base.
git checkout <branch-name>|Make the working directory and the HEAD match the specific branch.
git branch -d <branch-name> |Delete branch.
git rm <file>|Remove a file from the working directory (if applicable) and stop tracking the file.
 | 
How to recursively add the files in a directory|https://linuxprograms.wordpress.com/2012/01/30/git-how-to-recursively-add-the-files-in-a-directory/
Adding an existing project to GitHub using the command line|https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/
Rollback to last git commit| 
git reset --hard|To UNDO local file changes but NOT REMOVE your last commit, then use
git reset --hard HEAD~|To UNDO local file changes AND REMOVE your last commit, then use
git reset --soft HEAD~|To KEEP local file changes and REMOVE ONLY your last commit, then use
 |Use git status and git log frequently to observe your current state.
How to undo 'git add' before commit?| 
gir reset <file>|will remove it from the current index (the "about to be committed" list) without changing anything else.
git reset|without any file name to unstage all due changes. This can come in handy when there are too many files to be listed one by one in a reasonable amount of time
Cloning a repo on AWS and push back again| 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU3MzY0Mzg4Nl19
-->