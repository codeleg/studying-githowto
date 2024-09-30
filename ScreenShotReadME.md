
1. Screenshot: Configuring Git
The first step is to set up your name and email address in Git. We selected the main branch and wrote a command to fix line breaks (for Windows users).
    1. git config --global user.name "Your Name"
This sets your Git username globally.
    2. git config --global user.email "your_email@whatever.com"
This sets your Git email globally.
    3. git config --global init.defaultBranch main
This sets the default branch to "main" when you initialize a new repository.
For Windows users: 4. git config --global core.autocrlf true
This adjusts line endings to ensure compatibility between Windows and Unix-based systems.
    5. git config --global core.safecrlf warn
This gives a warning if files are checked out or committed with inconsistent line endings.

2. Screenshot: Creating a Local Repository and Connecting to a Remote Repository
This step shows how to create a local repository using Git and connect it to a remote repository.
    1. mkdir studying-git
This command creates a new directory named "studying-git." This directory will be used as the local Git repository.
    2. cd studying-git
This command moves into the "studying-git" directory. From now on, all Git commands will be executed inside this directory.
    3. git init
This initializes a new Git repository in the "studying-git" directory by creating a .git folder that contains all the necessary files for version control.
    4. git remote add origin https://github.com/codeleg/studying-git.git
This command adds a remote repository (the one on GitHub named "studying-git") to your local repository. The name "origin" is the default name given to the first remote repository.
    5. git pull origin main
This command pulls the latest changes from the "main" branch of the remote repository ("origin"). As shown on the screen, three objects (commit, string, etc.) were found in the remote repository and have been downloaded to the local one. This also creates the "main" branch locally.
    6. git add
This command stages files for the next commit, preparing the changes to be committed.
These steps are required to initialize a Git project and connect it to a remote repository.

3. Screenshot: Creating a Repository and Adding Files
Here, we show how to create a Git repository from a directory that contains one file and add that file to the repository.
    1. git add hello.html
This command adds the hello.html file to Git's staging area. This means that changes made to the file are being prepared for a future commit.
    2. git commit -m "Updated hello.html"
This commits the changes to the hello.html file, including a message ("Updated hello.html") describing the changes.
        ◦ The output [main 1b6ae69] Updated hello.html shows that the commit was successful, and it includes the commit hash (1b6ae69).
        ◦ 1 file changed, 1 deletion(-) means that one file was changed, and one line was deleted.
    3. git status
This command shows the current status of the Git repository. The output On branch main and nothing to commit, working tree clean indicates that there are no pending changes, and all changes have been committed.
At this point, the file has been added and the updates have been committed.

4. Screenshot: Committing Additional Changes
In this step, Git commands are used to manage and commit additional files:
    1. git commit -m "Update hello.html with new header"
This command commits the changes made to hello.html, with a message saying that the header was updated.
    2. git status
This command shows the current status of the Git repository. The output shows "Untracked files," indicating that files a.html, b.html, and c.html are not being tracked by Git yet, meaning they have not been added to the staging area.

Adding Files and Committing Changes:
    1. git add a.html
Adds a.html to the staging area.
    2. git add b.html
Adds b.html to the staging area.
    3. git commit -m "Commit changes"
Commits the staged changes with a descriptive message. However, the output shows that c.html hasn't been added yet.
    4. The first important aspect here is that Git knows about the c.html file and that it has been changed, but these changes have not yet been committed to the repository.
    5. git add c.html
Finally, c.html is added to the staging area.
File Structure:
On the left side, the file structure is shown under the path D:\MASAÜSTÜ\githowto\repositories\work\, which contains files hello.html, a.html, b.html, and c.html.

5. Screenshot: Status Check
    1. Status Check After making changes, the current status was checked:
        ◦ git status
This command shows which files have been modified and which ones are ready to be committed. The output indicates that the hello.html file has been modified.
    2. Commit Operation The changes have been committed:
        ◦ git commit -m "Added HTML header"
This command commits the changes to the hello.html file. The -m parameter allows adding a commit message, in this case, "Added HTML header." As a result of this operation, 1 file was modified with 2 additions.
    3. Final Status Check Finally, the status was checked again:
        ◦ git status
This command confirms that the current working directory is clean and all changes have been committed. The "working tree clean" message indicates that all modifications have been recorded.

6. Screenshot: Viewing the Project's History
The git log command allows you to get a list of changes made in the repository.
    • git log
You have full control over what the log displays. The single-line format is a favorite of many users:
Screenshot 6: git log --oneline
In this section, the commit history of the Git repository is summarized. The git log --oneline command shows each commit in a single line, providing a brief summary of commit messages.
    1. 780380e (HEAD -> main): Added HTML header
        ◦ This commit involves adding a header to the HTML file. The HEAD label indicates the commit you're currently working on.
    2. d52c5f: Added standard HTML page tags
        ◦ This commit adds standard HTML page tags.
    3. 085e211: Unrelated change to c
        ◦ This commit documents an unrelated change made to the c file.
    4. 95784d: Changes for a and b
        ◦ This commit involves changes made to the a and b files.
    5. 96395fd: Update hello.html with new header
        ◦ This commit adds a new header to the hello.html file.
    6. 1b6e069: Updated hello.html
        ◦ This commit signifies general updates made to the hello.html file.
    7. b385ee6: Initial commit
        ◦ This is the initial commit for the repository, representing the project's starting point.

    1. Customizing Git Log Format
        ◦ git log --pretty=format:"%h %ad %s (%an)" --date=short
This command shows the commit history in a custom format. For each commit, it shows:
            ▪ %h: The short commit hash
            ▪ %ad: The commit date (in short format)
            ▪ %s: The commit message
            ▪ %an: The author’s name
The --date=short parameter displays the date in a short format.
    2. Setting Global Date Format for Git Logs
        ◦ git config --global log.date short
This command globally sets the date format to short for all Git projects, so dates will always be shown in short format.
    3. Viewing Changes of a Specific Commit
        ◦ git show <commit-hash> -- work
This command shows the changes for a specific commit hash. The -- work parameter limits the view to changes in the "work" directory. However, since a valid commit hash was not provided, an error occurred.
    4. Viewing Changes for a Specific Commit (Example)
        ◦ git show 780380e
This command shows the changes related to the commit with the hash 780380e. The output shows the modifications made to the hello.html file. The HEAD label indicates that this is the commit you're currently working on.

5. git checkout 95d7844 -- b.html
This command attempts to restore the b.html file from the commit with hash 95d7844. However, an error message appears: "pathspec 'work' did not match any file(s) known to git." This indicates that Git doesn't recognize the specified file.
6. git checkout 95d7844 -- b.html
This command tries again to restore the b.html file, but the operation fails due to the same error message from the previous step.
7. git checkout 95d7844
This command checks out the 95d7844 commit. It returns the repository to the state it was in at that specific commit.

7. Screenshot:
    1. git log
This command displays the commit history of the Git repository. For each commit, the following information is shown:
        ◦ 780380e: The short commit hash.
        ◦ 2024-09-18: The commit date.
        ◦ Added HTML header: The commit message.
        ◦ (HEAD -> main): This indicates that you're currently on the main branch. Other commits are listed similarly.
    2. git checkout 5836970 -- Hello.html
This command attempts to restore the Hello.html file from the commit with the hash 5836970. However, the error message "fatal: invalid reference: 5836970" indicates that the specified commit hash is not valid.
    3. git checkout 95d784 -- hello.html
This command tries to restore the hello.html file from the commit with the hash 95d784. If successful, the content of the hello.html file will be updated to match its state at that commit.
    4. cat hello.html
This command displays the content of the hello.html file in the terminal. The output shows the file's content as <h1>Hello, World!</h1>.
    5. git switch main
This command switches to the main branch. The message "Already on 'main'" indicates that you are already on the main branch. Additionally, the output shows M hello.html, indicating that the hello.html file has been modified.
    6.  git checkout 95d7844 -- b.html
    7. This command tries again to restore the b.html file, but the operation fails due to the same error message from the previous step.
              7. git checkout 95d7844
    8. This command checks out the 95d7844 commit. It returns the repository to the state it was in at that specific commit.


7. Screenshot:
    1. git log
This command displays the commit history of the Git repository. For each commit, the following information is shown:
        ◦ 780380e: The short commit hash.
        ◦ 2024-09-18: The commit date.
        ◦ Added HTML header: The commit message.
        ◦ (HEAD -> main): This indicates that you're currently on the main branch. Other commits are listed similarly.
    2. git checkout 5836970 -- Hello.html
This command attempts to restore the Hello.html file from the commit with the hash 5836970. However, the error message "fatal: invalid reference: 5836970" indicates that the specified commit hash is not valid.
    3. git checkout 95d784 -- hello.html
This command tries to restore the hello.html file from the commit with the hash 95d784. If successful, the content of the hello.html file will be updated to match its state at that commit.
    4. cat hello.html
This command displays the content of the hello.html file in the terminal. The output shows the file's content as <h1>Hello, World!</h1>.
    5. git switch main
This command switches to the main branch. The message "Already on 'main'" indicates that you are already on the main branch. Additionally, the output shows M hello.html, indicating that the hello.html file has been modified.
8 Screenshot:
    1. git checkout v1
This command attempts to switch to the branch (or tag) named v1. However, an error message appears, warning that local changes will be lost. In this case, it is recommended to either save or stash your changes before proceeding.
    2. cat hello.html
This command is used to display the contents of the hello.html file. The file content is shown as "Hello, World!"
    3. git tag v1-beta
This command creates a tag named v1-beta on the current branch.
    4. git checkout v1
This command attempts to switch back to the v1 branch again, but this time information about a "detached HEAD" state is given. In this state, you are working on a temporary branch, and your changes may be lost unless properly committed.
    5. git switch <new-branch-name>
If you want to create a new branch, you can use this command to switch to it.
    6. git checkout v1-beta
This command switches to the v1-beta branch and shows the latest changes made in that branch.
    7. git tag -a -m "Added HTML header" v1-beta
This command creates an annotated tag with a message for the v1-beta tag. The message is "Added HTML header."
    8. git log --oneline --decorate
This command displays the commit history in a short format along with tags. Each commit is listed with a brief description and the branch or tag information.

9 Screenshot:
This section outlines the steps to manage the changes made to the hello.html file in a Git repository.
    1. git switch main
This command switches to the main branch. If you are already on this branch, the message "Already on 'main'" will be shown.
    2. git status
This command checks the status of files in the working directory. Here, it shows that hello.html has been modified but not yet committed. Under "Changes to be committed," it indicates that the file is staged but not yet committed.
    3. git restore --staged hello.html
This command removes the hello.html file from the staging area. If the file was staged for a commit, this command will undo that action.
    4. git status
After checking the status again, it shows that the changes to hello.html are still present in the working directory but no longer staged for commit.
    5. git checkout hello.html
This command restores hello.html to its state from the last commit, meaning any changes made to the file will be lost, and the file will revert to its previous version.
    6. git status
When checking the status again, the working directory is clean, indicating that all files match the state of the last commit with no changes present.
    7. cat hello.html
This command displays the contents of the hello.html file, which contains "Hello, World!"

10 Screenshot:

This section describes how to manage changes to the hello.html file in a Git repository:
    1. git add hello.html
This command stages the hello.html file. The changes made to the file are now ready for the next commit.
    2. git status
This command checks the status of the working directory. It indicates that you are on the main branch and that there are changes ready to be committed. The file hello.html is listed under "Changes to be committed."
    3. git reset HEAD hello.html
This command unstages the hello.html file, leaving the changes intact in the working directory but removing them from the staging area.
    4. git status
After checking the status again, it shows that hello.html has been modified but not yet staged for commit. The file appears under "Changes not staged for commit."
    5. git checkout hello.html
This command restores the hello.html file to the state of the last commit. Any changes to the file will be discarded, and the file will revert to its previous version.
    6. git status
After checking the status again, the working directory is clean, meaning all files match the state of the last commit.
These steps demonstrate how to manage file changes, stage, unstage, and revert changes in Git. It explains the process of handling file modifications and committing changes effectively. 
11 Screenshot:
This screenshot demonstrates the steps for managing changes to the hello.html file in a Git repository.
    1. git add hello.html
This command stages the hello.html file, meaning that the changes made to the file are ready for the next commit.
    2. git status
This command checks the status of files in the working directory. Here, it indicates that you are on the main branch and there are changes not yet committed. Under "Changes to be committed," it lists the hello.html file as being staged.
    3. git reset HEAD hello.html
This command unstages the hello.html file. The changes are still present in the working directory, but the file is no longer staged for commit.
    4. git checkout hello.html
This command restores the hello.html file to its state from the last commit. All changes will be discarded, and the file will revert to its previous version.
    5. git status
After checking the status again, the working directory is clean, meaning that all files are in their last committed state.
    6. git commit -m "Oops, we didn't want this commit"
This command commits the staged changes with the message "Oops, we didn't want this commit." It signifies that a commit is made but with a note that it may not have been intended.
    7. git revert HEAD
This command undoes the latest commit by creating a new commit that reverses the changes made in the previous one. The message "Waiting for your editor to close the file..." indicates that a text editor is opened to edit the revert commit message.
12 Screenshot:
This screenshot illustrates the steps for viewing the commit history and inspecting changes in a Git repository.
    1. cd work
This command changes the directory to work, where the Git repository is located.
    2. git log
This command displays the commit history for the current branch (in this case, the main branch). Each commit is listed with a unique identifier (hash), date, author, and commit message.
       Commit List:
        ◦ 5a1a178 (2024-09-19): "Revert 'Oops, we didn't want this commit'" – This is a revert commit to undo the effects of a previous commit.
        ◦ 1d0e76c (2024-09-18): "Oops, we didn't want this commit" – This commit contains unintended changes.
        ◦ 730280e (2024-09-18): "Added HTML header (tag: v1-beta, tag: v1)" – This commit adds an HTML header.
        ◦ daf25cf (2024-09-18): "Added standard HTML page tags" – This commit adds standard HTML tags.
        ◦ 08521a1 (2024-09-17): "Unrelated change to" – This commit contains an unrelated change.
        ◦ 957d84 (2024-09-17): "Changes for a and b" – This commit includes specific changes.
        ◦ 983f95d (2024-09-17): "Update hello.html with new header" – This commit updates the hello.html file with a new header.
        ◦ 1b6ace69 (2024-09-17): "Updated hello.html" – This commit updates the hello.html file.
        ◦ b385ee6 (2024-09-17): "Initial commit" – This is the initial commit of the project, marking its beginning.
These steps demonstrate how to view the commit history in Git and understand what changes each commit contains. The commit messages are important for explaining the changes made in each commit.

13 Screenshot:
This screenshot shows how a tag named "oops" was created using the command:
    • git tag oops: This command creates a tag called oops. Tags are generally used to mark specific commits or indicate version numbers.
    1. git reset --hard v1: This command resets the current working directory (HEAD) to the state of the commit tagged v1. The --hard parameter ensures that changes in the working directory are overwritten.
    2. git log: This command displays the commit history in the current state. The most recent commit has the hash 78038e0 with the message "Added HTML header."
    3. git log --all: This command shows the commit history for all branches and includes a list of commits and tags.
Summary of changes:
    • The v1 tag points to commit 78038e0, which added a header to an HTML page.
    • The oops tag marks a commit (1d0e76c) that was made by mistake. This commit was undone by the git reset --hard v1 command, returning to the state of the v1 tag.
These steps demonstrate how the state of the repository was restored by rolling back to the commit tagged as v1, effectively undoing the mistake marked by the oops tag.

14 Screenshot:
    • git tag -d opps: This command deletes the tag opps.
    • git log --all: This command shows the commit history for all branches and tags, displaying a full log list.
You can see that the opps tag has been deleted in this log

15 Screenshot:
    1. File Status:
        ◦ The hello.html file has been modified and is marked with an "M" (Modified) status, indicating that changes have been made.
    2. HTML Content:
        ◦ The hello.html file contains a basic HTML structure, including the author's name and a "Hello, World" heading. This file represents the fundamental structure of an HTML document.
    3. Git Log:
        ◦ Using the git log --all command, the full list of commits for the project is displayed. Each commit is identified by a unique hash, date, message, and branch.
    4. Commits:
        ◦ The commit messages show changes such as "Added HTML header" and "Added standard HTML page tags," which indicate the project's progression over time.
    5. File Staging:
        ◦ The git add hello.html command stages the changes made to the hello.html file, preparing it for commit.
    6. Amending Commit:
        ◦ The command git commit --amend -m "Added copyright statement with email" is used to modify the most recent commit, updating its message and adding new information. This commits the changes with the message "Added copyright statement with email," and updates the previous commit with this new data.
        ◦ The statement "1 file changed, 3 insertions (+)" summarizes the number of changes made in the commit.
    7. Latest Commit Status:
        ◦ Finally, the git log command shows the updated commit history, where the latest commit message has been updated to "Added copyright statement with email," reflecting the new changes from the amended commit.

16  Screenshot : The steps for creating a new branch, managing files, and committing changes in Git are outlined as follows:

Creating a New Branch and Checking Status:
    • $ git switch -c style: This command creates a new branch called style and switches to it. The -c option is shorthand for creating a new branch.
    • $ git status: After switching branches, this command checks the current status of the repository. The message "working tree clean" indicates that there are no uncommitted changes in the working directory at this point.

Creating a CSS File and Committing It:
    • $ touch style.css: This command creates a new empty file named style.css.
    • $ git add style.css: This stages the newly created style.css file, preparing it to be included in the next commit.
    • $ git commit -m "Added css stylesheet": This commits the staged changes with the message "Added css stylesheet," indicating the creation and addition of a new CSS file to the project.

Updating the HTML File:
    • $ git add hello.html: After updating the hello.html file (likely to include a link to the new CSS stylesheet), this command stages the changes to hello.html.
    • $ git commit -m "Included stylesheet into hello.html": This commits the staged changes with the message "Included stylesheet into hello.html," recording the update in which the new CSS file is linked to the HTML page.
Screenshot 17:
1. Viewing Commit History:
    • $ git log --all: This command displays the entire commit history of the project across all branches. Each commit includes a unique hash, timestamp, and message. The most recent commit is labeled with the message "Included stylesheet into hello.html," indicating the inclusion of a CSS stylesheet.
2. Switching to the Main Branch:
    • $ git switch main: This switches the working directory to the main branch, which is typically the primary branch for development.
3. Viewing the HTML File:
    • $ cat hello.html: This command outputs the content of hello.html in the terminal. The file likely includes basic HTML structure with an author name and the "Hello, World!" heading.
4. Switching to the Style Branch:
    • $ git switch style: This switches the branch to style, where the CSS stylesheet changes are made.
5. Viewing the Updated HTML File:
    • $ cat hello.html: Once again, this command displays the content of hello.html. This time, the file includes a link to the CSS file:

      <link type="text/css" rel="stylesheet" media="all" href="style.css" />
      This shows the inclusion of the style.css file, which is intended to style the HTML page.

Screenshot 18:
1. Viewing File Changes:
    • $ git status: This shows the current status of files in the working directory. The output indicates that hello.html has been deleted and renamed as index.html. Additionally, index.html is untracked, meaning it has not yet been added to version control.
2. Staging the Changes:
    • $ git add .: This stages all changes, including the renamed file (hello.html to index.html) and any other modifications, for the next commit.
3. Creating a New Folder:
    • $ mkdir css: This creates a new directory named css, which is typically used for organizing stylesheets.
4. Moving the Stylesheet:
    • $ git mv style.css css/style.css: This command moves the style.css file into the newly created css directory, organizing the project structure.
5. Checking the Status Again:
    • $ git status: This re-checks the file status after the changes. It confirms that style.css has been moved to css/style.css, and hello.html has been renamed to index.html.
6. Committing the Changes:
    • $ git commit -m "Renamed hello.html; moved style.css": This commits the staged changes with a message that reflects both the renaming of hello.html to index.html and the moving of style.css to the css folder.
7. Viewing Commit History:
    • $ git log: This command displays the commit history, with the latest commit detailing the file renaming and relocation.

These steps demonstrate how to rename files, move them into new directories, and maintain clear commit messages that describe the changes in a Git repository.

Here’s the translation of your content from Turkish to English for Screenshots 19 to 23:

Screenshot 19:
1. Viewing Commit History:
    • $ git log hello.html: The commit history for the hello.html file is displayed. The recent commits show the changes made to the file.
2. Viewing the Style File's History:
    • $ git log style.css: The commit history for the style.css file has been checked.
3. Viewing Last Commit Details:
    • $ git show v1: The details of the last commit associated with the v1 tag are displayed. This includes changes made to hello.html.
4. Viewing File Differences:
    • Changes in hello.html are shown, including the addition of a new <head> tag.
5. Renaming the File:
    • $ mv hello.html index.html: The hello.html file has been renamed to index.html.

Screenshot 20:
1. Switching Branches:
    • $ git switch main: Switched to the main branch, which is the primary development branch.
2. Adding a README File:
    • $ git add README.md: An attempt was made to add the README.md file. However, the error "pathspec 'README' did not match any files" indicates that the file does not exist.
3. Viewing the README File:
    • $ git add README.md: The content of the README.md file has been checked. The file contains the text: "This is the Hello World example from the GitHowTo tutorial."
4. Commit Operation:
    • $ git commit -m "Added README": A commit was made for the README file with the message "Added README." As a result, one file was changed and one addition was made.
Screenshot 21:
Viewing Commit History:
    • $ git log --all --graph: The commit history across all branches is displayed graphically. This allows for visual tracking of the project's development process and the changes made.

Here’s the translation of your content from Turkish to English for Screenshots 19 to 23:

Screenshot 19:
1. Viewing Commit History:
    • $ git log hello.html: The commit history for the hello.html file is displayed. The recent commits show the changes made to the file.
2. Viewing the Style File's History:
    • $ git log style.css: The commit history for the style.css file has been checked.
3. Viewing Last Commit Details:
    • $ git show v1: The details of the last commit associated with the v1 tag are displayed. This includes changes made to hello.html.
4. Viewing File Differences:
    • Changes in hello.html are shown, including the addition of a new <head> tag.
5. Renaming the File:
    • $ mv hello.html index.html: The hello.html file has been renamed to index.html.

Screenshot 20:
1. Switching Branches:
    • $ git switch main: Switched to the main branch, which is the primary development branch.
2. Adding a README File:
    • $ git add README.md: An attempt was made to add the README.md file. However, the error "pathspec 'README' did not match any files" indicates that the file does not exist.
3. Viewing the README File:
    • $ git add README.md: The content of the README.md file has been checked. The file contains the text: "This is the Hello World example from the GitHowTo tutorial."
4. Commit Operation:
    • $ git commit -m "Added README": A commit was made for the README file with the message "Added README." As a result, one file was changed and one addition was made.

Screenshot 21:
Viewing Commit History:
    • $ git log --all --graph: The commit history across all branches is displayed graphically. This allows for visual tracking of the project's development process and the changes made.

Screenshot 22:
1. Switching Branches:
    • $ git switch style: Switched to the style branch, where changes related to styles are made.
2. Merging with the Main Branch:
    • $ git merge main: Merged the main branch into the style branch. This operation brings changes from the main branch into the style branch.
3. Merge Operation:
    • The message "Merge made by the 'ort' strategy." indicates that the merge was performed using the 'ort' strategy, which is an automatic merging method.
4. Creation of the README File:
    • The README.md file was created, and one line was added. This file will contain the project's descriptions and information.
5. Viewing Commit History:
    • $ git log --all --graph: The commit history across all branches is displayed graphically.
    • bae7219 (2024-09-19): The main branch was merged into the style branch.
Screenshot 23:
1. HTML File Content:
    • The hello.html file has a basic HTML structure. Its content is as follows:
    • 
      <!-- Author: Alexander Shvets (alex@githowto.com) -->  
      <html>  
        <head>  
          <meta charset="UTF-8">  
          <title>Hello World Page</title>  
        </head>  
        <body>  
          <h1>Hello, World!</h1>  
          <p>Let's learn Git together.</p>  
        </body>  
      </html>  
2. Switching Branches:
    • $ git switch main: Switched to the main branch, which is the primary development branch.
3. Adding the File and Commit Operation:
    • $ git add hello.html
    • $ git commit -m "Added meta charset": The hello.html file was added, and it was committed with the message "Added meta charset." This resulted in one file being changed, with five additions and two deletions.
4. Viewing Commit History:
    • $ git log --all --graph: The commit history across all branches is displayed graphically. This allows for visual tracking of the project's development process and the changes made.
5. Last Commit Details:
    • bae7719 (2024-09-19): The main branch was merged into the style branch.
24 Screenshot
Branch Switching
    • $ git switch style
◦ Switched to the style branch, defined as the branch where style-related changes are made.
Merge Operation
    • $ git merge main
◦ Attempted to merge the main branch with the style branch. However, a conflict occurred in the hello.html file. The error message indicates that the hello.html file was deleted in HEAD and modified in the main branch.
Status Check
    • $ git status
◦ Checked the status of the style branch due to the conflict. Files that had conflicts are listed under "Unmerged paths."
Conflict Resolution
    • $ git add index.html
◦ Attempted to add the index.html file, but the operation failed due to the conflict. It was indicated that the conflict needs to be resolved.
Conflict Resolution and Commit
    • $ git commit -m "Resolved merge conflict for hello.html"
◦ After resolving the conflict in the hello.html file, a commit was made. This indicates that the conflict was successfully resolved and the changes were saved.
Status Check
    • $ git status
◦ Checked that the working tree is clean. This means that all changes have been saved and conflicts have been resolved.
Commit History Viewing
    • $ git log --graph --oneline --decorate
◦ The commit history was displayed graphically. This allows for visual tracking of the project's development process and changes made.
Last Commit Details
    • ◦ 8bd270e (HEAD -> style): Resolved conflict in hello.html.
    • ◦ dea0c4f (main): Added meta charset.
25 Screenshot
Adding Remote Repository
    • $ git remote add origin https://github.com/codeleg/studying-githowto.git
◦ A remote repository named origin has been added. This specifies the remote extension of the local repository on GitHub.
Pushing Changes
    • $ git push --force origin style
◦ Attempted to forcefully push the style branch to the remote origin repository. This operation synchronizes local changes with the remote repository.
Push Operation Details
    • ◦ "Enumerating objects" and "Counting objects" messages indicate the number of objects to be sent.
    • ◦ "Compressing objects" and "Delta compression" messages show that the data being sent is being compressed.
    • ◦ "Resolving deltas" message indicates that delta calculations are being performed during the send operation.
Creating Pull Request
    • ◦ After the push operation is completed, a message provides a link to create a pull request for the 'style' on GitHub. This facilitates the request to merge changes made in the remote repository with the main branch.
Viewing Remote Repository Information
    • $ git remote -v
◦ The information of the remote repository has been displayed. The URL of the repository added under the name origin is shown.

26 Screenshot
Viewing Commit History
    • $ git log --graph
◦ The commit history was displayed graphically. This allows for visual tracking of the project's development process and changes made.
Last Commit Details
    • ◦ 3e94895 (2024-09-19): hello.html file was renamed, and style.css file was moved.
    • ◦ c491b74 (2024-09-19): Style added to hello.html file.
    • ◦ da5c1f4 (2024-09-18): Copyright notice added.
    • ◦ 0a6f5d4 (2024-09-18): Standard HTML page tags added.
    • ◦ e58b21c (2024-09-18): Changes a and b were made.
    • ◦ b386e69 (2024-09-17): First commit.
Resetting HEAD to a Specific Commit
    • $ git reset --hard HEAD-2
◦ HEAD has been reset to two commits ago. This operation reverts the working tree and index to the specified commit.
Checking Current State of HEAD
    • $ git log --graph
◦ After the reset operation, the commit history was viewed again. This shows the current state of HEAD and which commit it has reverted to.
Last Commit Status
    • ◦ 4c91b74 (HEAD -> style): CSS style file added.
27 Screenshot
Checking Branch Status
    • $ git log --all --graph
◦ Checked that you are on the style branch and that the commit history was displayed graphically. This allows for visual tracking of the project's development process and changes made.
Last Commit Details
    • ◦ b29f2c9 (HEAD -> style): hello.html file was restored.
    • ◦ 4dcf1d7: style.css file was moved.
    • ◦ b2f9c4e: Merge conflict in README.md was resolved.
    • ◦ 420e40f: Changes made to index.html.
    • ◦ eea4a05: hello.html file was restored.
Attempt to Push to Remote Repository
    • $ git push origin style
◦ When attempting to push the style branch to the remote repository, the "failed to push some refs" error occurred. This indicates that the local branch is behind the remote branch.
Fetching Updates from Remote Repository
    • $ git pull origin githowto
◦ Attempted to fetch updates from the remote repository. This operation updates the local branch.
Conflict Situation
    • ◦ It was indicated that there is a conflict in the index.html file. It was stated that the conflict needs to be resolved.
Resolving the Conflict
    • ◦ The conflict must be resolved, and then the changes should be committed. This operation synchronizes local changes with the remote repository.
Retrying Push
    • $ git push origin style
◦ After resolving the conflict, an attempt was made to push the style branch to the remote repository. The "Everything up-to-date" message indicates that the local branch is synchronized with the remote branch.
28 Screenshot
Conflict Situation
    • ◦ It was indicated that there is a conflict in the index.html file. The conflict is attempted to be resolved with the command git add index.html.
    • ◦ Before resolving the conflict, the command git commit -m "Resolve merge conflict in index.html" was used to commit the conflict resolution.
Push Operation
    • $ git push origin style
◦ Attempted to push the style branch to the remote repository. This operation synchronizes local changes with the remote repository.
Branch Switching
    • $ git switch main
◦ Switched to the main branch to continue working on the main branch of the project.
Viewing Commit History
    • $ git log --all --graph
◦ The commit history was displayed graphically. This allows for visual tracking of the project's development process and changes made.
Differences from Previous Steps
    • Conflict Resolution: In previous steps, conflicts were not resolved. In this step, the conflict in the index.html file was resolved and committed.
    • Push Operation: In previous steps, the push operation had failed. In this step, after resolving the conflict, the style branch was successfully pushed to the remote repository.
    • Branch Switching: In previous steps, only the style branch was being worked on. In this step, switched to the main branch.
    • Viewing Commit History: In previous steps, the commit history was not viewed. In this step, the commit history was checked graphically.
THIS PART IS THE PART THAT GOES TO STEP 30 IN THE HOW PROJECT.
PART WORK 2 

ScreenShot 30 
Change Directory: The command cd . is used to change the current directory to the current directory itself, which doesn't change anything but is often used to refresh the terminal's context.
    1. Print Working Directory: The command pwd displays the current working directory, which is /d/MASAUSTU/githowto/repositories.
    2. List Directory Contents: The command ls lists the contents of the current directory. In this case, it shows a directory named work.
    3. Clone a Repository: The command git clone work home is used to clone the work directory into a new directory named home. The terminal indicates that the cloning process is complete with the message "done."
    4. List Directory Contents Again: The command ls is used again to list the contents of the current directory, which now includes the newly created home directory.
the steps involve navigating to a directory, checking its contents, and cloning a repository from one directory to another. 
 31  ScreenShot
Change Directory:
        ◦ Command: cd home
        ◦ This command changes the current working directory to the home directory.
    2. List Directory Contents:
        ◦ Command: ls
        ◦ This command lists the files and directories in the home directory. The output shows:
            ▪ LICENSE
            ▪ README.md
            ▪ b.html
            ▪ c.html
            ▪ hello.html
            ▪ index.html
            ▪ screenshots
            ▪ css
    3. View Git Log:
        ◦ Command: git log --all --graph
        ◦ This command displays the commit history in a graphical format, showing all branches. The output includes:
            ▪ The latest commit (e47c962) indicates a merge from the main branch.
            ▪ Each commit is listed with its hash, date, and a brief message describing the changes made.
Key Points from the Git Log Output:
    • Commit Messages: Each entry shows what was done in that commit, such as deleting files, creating screenshots, resolving merge conflicts, and adding files.
    • Branching and Merging: The log indicates that the main branch was merged, which is a common practice in collaborative projects to integrate changes from different branches.
    • Commit Hashes: Each commit has a unique identifier (hash) that can be used to reference specific changes.
Overall, this session involves navigating to a directory, listing its contents, and reviewing the commit history of a Git repository.

32 ScreenShot
1. Change Directory
    • Command: cd home
    • Explanation: This command changes the current working directory to the home directory within the specified path.
2. List Remote Repositories
    • Command: git remote
    • Explanation: This command lists the remote repositories associated with the local Git repository. The output shows:
        ◦ origin: This is the default name for the remote repository.
3. Show Remote Repository Details
    • Command: git remote show origin
    • Explanation: This command provides detailed information about the remote repository named origin. The output includes:
        ◦ Fetch URL: D:/MASAÜSTÜ/githowto/repositories/work - This is the URL from which the repository can be fetched.
        ◦ Push URL: Same as the fetch URL, indicating where changes can be pushed.
        ◦ HEAD branch: main - This indicates that the default branch of the remote repository is main.
        ◦ Remote branches: Lists the branches available in the remote repository:
            ▪ backup-main: tracked
            ▪ main: tracked
            ▪ style: tracked
        ◦ Local branch configured for 'git pull': Indicates that the local main branch is set to merge with the remote main branch.
        ◦ Local ref configured for 'git push': Indicates that local changes will be pushed to the main branch of the remote repository, and it is up to date.
33 ScreenShot 
git branch
Description: This command lists the branches in the current Git repository.
Output:
    • * main: This indicates that you are currently on the main branch. The asterisk signifies the active branch.
    • git branch -a
Description: This command lists both local and remote branches.
Output:
    • * main: Again, the active branch is main.
    • remotes/origin/HEAD -> origin/main: This shows that the default branch in the remote repository named origin is main.
    • remotes/origin/backup-main: Another branch located in the remote repository.
    • remotes/origin/main: The main branch in the remote repository.
    • remotes/origin/style: Another branch present in the remote repository.
34 ScreenShot
1. Change Directory
    • Command: cd ..
    • Explanation: This command moves up one directory level to the parent directory.
2. Change to Work Directory
    • Command: cd work
    • Explanation: This command changes the current working directory to the work directory.
3. Add README File
    • Command: git add README
    • Explanation: This command stages the README file for the next commit. However, the output indicates that the file path specified did not match any files.
4. Commit Changes
    • Command: git commit -m "Changed README in original repo"
    • Explanation: This command attempts to commit the staged changes with a message. The output indicates:
        ◦ On branch main: You are currently on the main branch.
        ◦ Changes not staged for commit: The system informs you that there are changes in the working directory that have not been staged.
        ◦ Modified: The README.md file has been modified but not staged.
5. Add README.md File Again
    • Command: git add README.md
    • Explanation: This command stages the README.md file for the next commit.
6. Commit Changes Again
    • Command: git commit -m "Changed README in original repo"
    • Explanation: This command commits the changes with the specified message. The output indicates:
        ◦ 1 file changed: The README.md file was modified.
        ◦ 2 insertions(+): Two lines were added to the file.
        ◦ 2 deletions(-): Two lines were removed from the file.
35 ScreenShot
Fetch Updates:
        ◦ Command: git fetch
        ◦ This command retrieves updates from the remote repository without merging them into the local branch.
    2. View Commit History:
        ◦ Command: git log --all --graph
        ◦ This command displays the commit history in a graphical format, showing all branches and their relationships.
    3. Key Outputs:
        ◦ The log shows various commits, including changes to the README.md file and merges from different branches.
        ◦ It indicates the most recent changes and conflicts resolved during the development process.

36 ScreenShot
View README File:
        ◦ Command: cat README.md
        ◦ This command displays the contents of the README.md file, which includes a brief description of the project.
    2. Merge Changes:
        ◦ Command: git merge origin/main
        ◦ This command merges changes from the remote main branch into the local branch. The output indicates:
            ▪ The commit being updated (e47c962...).
            ▪ A fast-forward merge occurred, meaning the local branch was simply updated to match the remote branch.
            ▪ The README.md file was modified with 2 insertions and 2 deletions.
    3. Check for Updates:
        ◦ Command: git pull
        ◦ This command checks for any new changes from the remote repository. The output indicates that the local branch is already up to date, meaning there are no new changes to pull.

37 ScreenShot 
Track a New Branch:
        ◦ Command: git branch --track style origin/style
        ◦ Explanation: This command creates a new local branch named style that tracks the remote branch origin/style. The output confirms that the branch has been set up to track the remote branch.
    2. List Local Branches:
        ◦ Command: git branch
        ◦ Explanation: This command lists all local branches. The output shows:
            ▪ * main: Indicates that the current active branch is main.
            ▪ style: The newly created branch is also listed.
    3. List All Branches:
        ◦ Command: git branch -a
        ◦ Explanation: This command lists all local and remote branches. The output includes:
            ▪ remotes/origin/HEAD -> origin/main: Indicates the default branch for the remote repository.
            ▪ Other remote branches: backup-main, main, and style.
    4. View Commit History:
        ◦ Command: git log --max-count=2
        ◦ Explanation: This command displays the last two commits in the repository. The output shows:
            ▪ The most recent commit where the README was changed.
            ▪ A merge commit indicating that the main branch was merged from a remote repository.
Summary
This session demonstrates creating a new branch that tracks a remote branch, listing local and remote branches, and reviewing the recent commit history. It highlights the process of managing branches and tracking changes in a Git repository.
 
38 ScreenShot
View Recent Commits:
        ◦ Command: git log --max-count=2
        ◦ Explanation: This command displays the last two commits in the repository. The output shows:
            ▪ The most recent commit where the README was changed.
            ▪ A merge commit indicating that the main branch was merged from a remote repository.
    2. Change Directory:
        ◦ Command: cd ..
        ◦ Explanation: This command moves up one directory level to the parent directory.
    3. Clone a Bare Repository:
        ◦ Command: git clone --bare work.git
        ◦ Explanation: This command clones a bare repository named work.git. The output confirms that the cloning process was successful.
    4. List Contents of the Directory:
        ◦ Command: ls work.git
        ◦ Explanation: This command lists the contents of the work.git directory. The output shows:
            ▪ Various directories and files related to the Git repository, such as hooks, info, objects, and refs.
Summary
This session demonstrates viewing recent commits, changing directories, cloning a bare repository, and listing its contents. It highlights the process of managing repositories and understanding their structure in Git.
39 ScreenShot
cd work
Description: This command changes the current directory to the work directory. The cd command stands for "change directory." By executing this command, you are navigating into the work folder, which is presumably where your Git repository is located.
    • git remote add shared ../work.git
Description: This command adds a new remote repository to your Git configuration. Here’s a breakdown of the command:
    • git remote add: This is the Git command used to add a new remote repository. A remote repository is a version of your project that is hosted on the internet or another network.
    • shared: This is the name you are giving to the remote repository. You can choose any name, but it’s common to use descriptive names that indicate the purpose or type of the remote.
    • ../work.git: This specifies the location of the remote repository you are adding. The .. refers to the parent directory of the current directory (i.e., the directory one level up). So, ../work.git indicates that the shared remote repository is located in the parent directory and is named work.git.
40 ScreenShot
View README File:
        ◦ Command: cat README.md
        ◦ Explanation: This command displays the contents of the README.md file, which includes a description of the project.
    2. Switch to Main Branch:
        ◦ Command: git switch main
        ◦ Explanation: This command switches to the main branch. The output indicates that you are already on the main branch.
    3. Stage Changes:
        ◦ Command: git add README.md
        ◦ Explanation: This command stages the README.md file for the next commit.
    4. Commit Changes:
        ◦ Command: git commit -m "Added shared comment to readme"
        ◦ Explanation: This command commits the staged changes with a message. The output shows that one file was changed, with one insertion and one deletion.
    5. Push Changes to Remote:
        ◦ Command: git push shared main
        ◦ Explanation: This command pushes the changes from the local main branch to the remote repository named shared. The output confirms that the push was successful, showing the objects being counted and written.
Summary
This session demonstrates viewing the README.md file, switching to the main branch, staging and committing changes, and pushing those changes to a remote repository. It highlights the process of updating documentation and sharing changes in a Git environment.
41 ScreenShot
Change Directory:
        ◦ Command: cd ..
        ◦ Explanation: This command moves up one directory level to the parent directory.
    2. Pull Changes from Remote:
        ◦ Command: git pull shared main
        ◦ Explanation: This command pulls changes from the main branch of the remote repository named shared. The output indicates:
            ▪ Objects are being enumerated, counted, and compressed.
            ▪ A fast-forward merge occurred, updating the local branch to include the latest changes.
    3. View README.md File:
        ◦ Command: cat README.md
        ◦ Explanation: This command displays the contents of the README.md file, which includes a description of the project. The output shows that the file was modified, with one insertion and one deletion.
Summary
This session demonstrates changing directories, pulling updates from a remote repository, and viewing the contents of the README.md file. It highlights the process of synchronizing local changes with a remote repository in Git.


42 ScreenShot
Clone a Repository:
        ◦ Command: git clone git://localhost/work.git network_work
        ◦ Explanation: This command clones a repository from a local Git server into a new directory named network_work. The output indicates:
            ▪ Objects are being counted and received, confirming the cloning process was successful.
    2. Change Directory:
        ◦ Command: cd network_work
        ◦ Explanation: This command navigates into the newly created network_work directory.
    3. List Directory Contents:
        ◦ Command: ls
        ◦ Explanation: This command lists the contents of the network_work directory, showing files like LICENSE, README.md, and various HTML files.
    4. Start Git Daemon:
        ◦ Command: git daemon --verbose --export-all --base-path=.
        ◦ Explanation: This command starts a Git daemon to serve repositories over the network. The output shows:
            ▪ Connection attempts and errors related to socket input/output.
            ▪ Extended attributes and requests for upload packs.
Summary
This session demonstrates cloning a local Git repository, navigating into the cloned directory, listing its contents, and attempting to start a Git daemon for network access. It highlights the process of setting up and accessing Git repositories in a local environment.
 Thank you for 
Alexander Shvets
alex@githowto.com 