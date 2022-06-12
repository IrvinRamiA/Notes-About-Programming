# Git Quick Manual

## Upload local project to GitHub

1. Go to the project directory.
2. First create a new repository in this directory: $ git init
3. The default branch is "master".
4. Now you can tell Git about your files by adding them to your repository:
* $ git add . (to add all folders and files).
* $ git add folder_name/file_name
5. Commit your changes so Git can track them: $ git commit -m "First commit"

To push the changes to your Git repository hosted with GitHub:

6. Create a new repository in GitHub.
7. Add a remote location: $ git remote add origin https://github.com/yourusername/your-repo-name.git
8. Now Git knows about your remote repository. You can tell it to push your
committed files:
$ git push -u origin master


## Git Ignore

1. Add a file named ".gitignore" to the project root folder.
2. Write the folders or files that you want to be ignored. For example:
* .vscode
* docs
* Notes.md
