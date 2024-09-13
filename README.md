# Git + GitHub for Macbook

## I will teach how to make a GitHub repository using Git for the Macbook users.

### 1º: Creating a repository on GitHub
* First, we need a [GitHub](https://github.com/) account and then let's create a repository.
* On the page, it has two options to create: `private` or `public` repository. You must choose what you prefer, if it's a private repository that only you can see, or a public that anyone who access your page can visit.
* After choose the kind of repository you want, just click on `create a new repository`.
  
![GitHub Repository](/images/repository.png)

* After just click on the circled option and the README option. Then create the repository by clicking the “Create repository” button at the bottom of the page.

![README](/images/readme.png)
* You can edit with instructions from your repository or whatever you want to describe about your work. People often create to provide the "repository manual".
  
* To get ready to copy (clone) this repository onto your local machine, click the green “Code” button, which should be to the right of the button displaying the current branch (typically it will display the main branch). Then select the SSH option in the “Clone” section, and copy the line below it. **NOTE: You MUST click the SSH option to get the correct URL**.

![Clone](/images/clone.png)

### 2º: Creating a repository on the local machine

* Let's open the terminal by clicking on the `spotlight` button or `cmd + space`  and type `terminal`.
* Before we start, Github recently updated the way it names the default branch. This means you need to make sure you are using a recent version of git (2.28 or later). You can check your version by running: `git --version`.
* If you haven’t already, set your local default Git branch to `main`. You can do so by running: `git config --global init.defaultBranch main`
* Next get back to the Terminal and just paste some basic commands:
```
mkdir repos
cd repos
```
* Doing that, it will create a directory named `repos` on your Macbook central directory (you can name it whatever you prefer). This folder will represent the directory that you will work and upload on GitHub.
* To link the directory on GitHub you will use the `git clone` and the `URL` that was copied on SSH Option to the terminal.
```
git clone git@github.com:USER-NAME/REPOSITORY-NAME.git
```
* Notice that I putted `USER-NAME/REPOSITORY-NAME` that you will replace to your own user name and repository name, finishing with `.git`.
