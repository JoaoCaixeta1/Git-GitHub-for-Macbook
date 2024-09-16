# Git + GitHub for Mac

## I will teach how to make a GitHub repository using Git for the Mac users.

### 1º: Creating a repository on GitHub
* First, we need a [GitHub](https://github.com/) account and then let's create a repository.
* On the page, it has two options to create: `private` or `public` repository. You must choose what you prefer, if it's a private repository that only you can see, or a public that anyone who access your page can visit.
* After choose the kind of repository you want, just click on `create a new repository`.
* After just click on the circled option and the README option. Then create the repository by clicking the “Create repository” button at the bottom of the page.

![GitHub Repository](/images/repository.png)

* You can edit with instructions from your repository or whatever you want to describe about your work. People often create to provide the "repository manual".
  
* To get ready to copy (clone) this repository onto your local machine, click the green “Code” button, which should be to the right of the button displaying the current branch (typically it will display the main branch). Then select the SSH option in the “Clone” section, and copy the line below it. **NOTE: You MUST click the SSH option to get the correct URL**.

![Clone](/images/clone.jpg)

### 2º: Creating a repository on the local machine

* Let's open the terminal by clicking on the `spotlight` button or `cmd + space`  and type `terminal`.
* Before we start, Github recently updated the way it names the default branch. This means you need to make sure you are using a recent version of git (2.28 or later). You can check your version by running: `git --version`.
* If you haven’t already, set your local default Git branch to `main`. You can do so by running:
```
git config --global init.defaultBranch main
git status
```
* Next get back to the Terminal and just paste some basic commands:
```
mkdir repos
cd repos
```
* Doing that, it will create a directory named `repos` on your Mac central directory (you can name it whatever you prefer). This folder will represent the directory that you will work and upload on GitHub.
* To link the directory on GitHub you will use the `git clone` and the `URL` that was copied on SSH Option to the terminal.
```
git clone git@github.com:USER-NAME/REPOSITORY-NAME.git
```
* ***Notice that I putted `USER-NAME/REPOSITORY-NAME` that you will replace to your own user name and repository name, finishing with `.git`.***
* Congrats, you have connected your GitHub repository to your local machine. To test:
```
cd REPOSITORY-NAME
git remote -v
```
* You should see an output similar to the following, where `USER-NAME` is your GitHub username:
```
  origin  git@github.com:USER-NAME:git_test.git (fetch)
  origin  git@github.com:USER-NAME:git_test.git (push) 
```
* This displays the URL of the repository you created on GitHub, which is the remote for your local copy. You may have also noticed the word origin at the start of the git remote -v output, which is the name of your remote connection. The name “origin” is both the default and the convention for the remote repository, but it could have just as easily been named “Star-Wars” or “Dancing-frog”.

### 3º: Logging changes with Git

* Let's create a new file on your REPOSITORY-NAME. Type on terminal `touch "hello_world.txt"`
* Know type `git status` to see that your "hello_world.txt" is shown with a red text color, because it means that the file is not yet staged.
* To get staged, type `git add hello_world.txt`. Now the file is in the staging area waiting to be committed. This is an "two staged" process that Git provides to confirm the file and repository regist. You can type `git status` to see that the file is now shown with a green color.
* Finishing the commit, type:
```
git commit -m "Add hello_world.txt"
git status
```
* The output should now say: “nothing to commit, working tree clean”, indicating your changes have been committed.
* Don’t worry if you get a message that says “upstream is gone”. This is normal and only shows when your cloned repository currently has no branches. It will be resolved once you have followed the rest of the steps in this project. The message, “Your branch is ahead of ‘origin/main’ by 1 commit” just means that you now have newer snapshots than what is on your remote repository. You will be uploading your snapshots further down in this lesson.
* If this happen. Type git log and look at the output. You should see an entry for your “Add hello_world.txt” commit. You will also see other details which include the author who made the commit and the date and time of when the commit was made. If your terminal is stuck in a screen with (END) at the bottom, just press “q” to escape. You can configure settings for this later, but don’t worry about it too much for now.

### 4º: Modifing and saving a file

* Open the "hello_world.txt" in your text editor of choice (I prefer use `Text Editor` or `Visual Studio Code`) and type anything like "Cruzeiro Esporte Clube" and save the changes.
* Now type:
```
git add hello_world.txt
git status
git commit -m "Edit hello_world.txt"
git status
```

### 5º: Push your work to GitHub

* Finally, let’s upload your work to the GitHub repository you created at the start of this tutorial.
* Type `git push origin main`. NOTE: If at this point you receive a message that says “Support for password authentication was removed on August 13, 2021. Please use a personal access token instead.”, you have followed the steps incorrectly and cloned with HTTPS, not SSH. Please follow the steps for switching remote URLs from HTTPS to SSH to change your remote to SSH, then attempt to push to Github.
* Type `git status` one final time. It should output “Your branch is up to date with ‘origin/main’. nothing to commit, working tree clean”.
* And when you refresh your GitHub it will have your new files.
