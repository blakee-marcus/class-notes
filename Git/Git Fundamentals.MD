# Git Fundamentals

## Pushing

Pushing changes to a GitHub repository means sending any changes you've made to the repository on your local machine up to the repository on GitHub.

When you commit changes to a Git repository, you're creating a snapshot of the code at a particular point in time. These snapshots are stored in the repository's history, and each commit represents a specific set of changes made to the code.

When you push commits to a remote repository, such as a repository on GitHub, you're sending those commits to the remote repository. This allows other people who have access to the repository to see the changes you've made and work with them.

When you push changes to a remote repository, it's important to be aware of any changes that may have been made by other collaborators since your last pull. If there are conflicts between your changes and changes made by others, you'll need to resolve those conflicts before pushing your changes.

In general, it's a good practice to pull changes from the remote repository before pushing changes to it, to ensure that you have the latest version of the code and can avoid conflicts.

1. Open Git Bash on your local machine.

2. Navigate to the local directory where the repository is cloned. You can use the cd command to change directories, like this: `cd path/to/repository`

3. Once you are in the repository directory, make changes to the code as needed.

4. After making changes, you need to stage your changes using the git add command. This command adds any changes you've made to the staging area, which prepares them to be committed. For example, if you want to stage all changes made to all files, you would run the command: `git add .`

5. Next, you need to commit your changes to the repository using the git commit command. This command creates a new commit with the changes you've staged. Be sure to add a commit message that describes the changes you've made. For example: `git commit -m "Added new feature"`

6. Finally, you need to push your changes to the remote repository on GitHub using the git push command. This command sends the changes you've committed to the remote repository. You'll need to specify the remote repository and the branch you want to push to. For example: `git push origin main`

7. If you haven't already, you'll need to authenticate with your GitHub account. Git Bash may prompt you to enter your username and password, or you may need to set up SSH authentication if you haven't already.

8. Once the push is complete, you should see a message indicating that the changes were pushed successfully.

## Pulling

1. Open Git Bash on your local machine.

2. Navigate to the local directory where the repository is cloned. You can use the cd command to change directories, like this: `cd path/to/repository`

3. Once you've fetched any changes from the remote repository, you can pull those changes to your local repository using the `git pull command`. This command downloads any changes made to the remote repository and merges them with your local repository. For example: `git pull origin main`