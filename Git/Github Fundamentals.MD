# Github Fundamentals

## Create a Github Repository

1. First, you need to create a GitHub account. If you don't already have one, go to the [GitHub website](https://www.github.com) and sign up for a free account.

2. Once you're signed in to GitHub, click on the "+" icon in the top right corner of the page and select "New repository" from the dropdown menu.

3. In the "Create a new repository" page, you'll need to provide a name for your repository, a brief description (optional), and decide whether it should be public or private. A public repository can be accessed by anyone, while a private repository requires specific permission to access.

4. You can also choose to initialize your repository with a README file, which is a good idea if you want to provide some basic information about your project. Additionally, you can select a license for your repository, which will determine how others can use your code.

5. Once you've filled in the necessary information, click the "Create repository" button to create your new repository.

6. Your new repository will now be created on GitHub, and you'll be taken to the repository page. From here, you can add files to your repository, manage your repository settings, and collaborate with others by inviting them to contribute to your project.

That's it! You've now created a new repository on GitHub. You can now clone your repository to your local machine using Git Bash, add files, and push changes back to GitHub using Git commands.
***

## Clone/Pull a Github Repository

When you clone a repository, you create a local copy of the repository on your machine. This copy is a fully functional Git repository that you can use to make changes and track changes over time.


1. Open Git Bash on your local machine.

2. Navigate to the directory where you want to clone the repository. You can use the `cd` command to change directories, like this: `cd path/to/directory`

3. Once you are in the desired directory, go to the GitHub repository that you want to clone and click on the "Code" button.

4. You'll see a dropdown menu with options to clone the repository using HTTPS, SSH, or GitHub CLI. Click on the "SSH" option to clone the repository using SSH.

5. Copy the SSH clone URL that is displayed.

6. Go back to Git Bash and type the following command: `git clone <clone_url>`, replacing `<clone_url>` with the SSH clone URL you just copied. For example: `git clone git@github.com:username/repository.git`

7. Press enter, and Git Bash will begin cloning the repository to your local machine.

8. If you haven't already, you'll need to add your SSH key to your GitHub account. Follow the instructions on the GitHub documentation to do this: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

9. Once the cloning process is complete, you should see a message indicating that the repository was cloned successfully.
