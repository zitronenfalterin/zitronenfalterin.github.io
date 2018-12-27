Git for beginners workshop
==========================


## Install git

Follow the guides here: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

for windows: you can additionally follow this tutorial: http://guides.beanstalkapp.com/version-control/git-on-windows.html (only the Installing Git section, we will do SSH keys later)

## Let's start with a local repository

create a folder (your new project) and create a .txt file within this folder.
Rund '''git init [path/to/this/folder]''' on the command line. This will create a .git folder within your project.

run '''git status''' on the command line. Change the text file. Run '''git status''' again.

run '''git add .''' and afterwards '''git commit -m "started my first git project"'''

This will add all changed files to the list of tracked files. Git commit will track the file changes.

run '''git log''' and you can see, that you have now one commit in the list. With the commit name, you can always go back to this version of your project.

Now that you have a local git project, it's time to create a github account.


## Create a github account

Github is one of the services, where you can store your code remotely. It's for free, as long as the repository is public. Github was bought by Microsoft and is by far the biggest service, but there are others which do bascially the same. Most of the workshop can be done without a github account, but it's easiest if you create an account now. Alternatives are, for example, gitlab or  bitbucket, etc.

## Set up an SSH key
run ssh-keygen on the command line. This will create a public and a private SSH key for you, which you can use to conveniently access your github account via the command line without entering your github password every time. Remember where your computer stores the two generated files. (On linux, it's usually a .ssh folder in your home. (The dot in ".ssh" means, that it is a hidden folder.)

In github, go to your account settings -> SSH and GPG keys. Click on "new SSH key" and then copy and paste the created *Public* key into github.

## Create a repository in github

In your github account, go to repositories and create a new empty repo (no readme, no gitignore, no license). Follow the "…or push an existing repository from the command line" steps that github shows you on the next page. This will publish your local file on github.



Collaborate with git
====================

The main reason why git was created and why it is used so much is, that it helps you to work together. This is done by "branching" from the main project, working on that branch and then "pushing" the work back into the "master branch" when it is ready. We can try this together.


## Clone this repository

In github, click on the green "Clone or download" button. choose "use SSH". This will copy the path.

In your command line enter: git clone [past the copied path here]

Now you have this little workshop repository locally. By default, you are in the "master" branch. 

## Create a local branch

Run '''git checkout -b [your nickname-branch]

run '''git branch'''. This will show you the list of branches for this project on your computer. It should also show you that you are currently in the branch you just created. The folder contains a very basic HTML website. Open the file with your number in an editor (e.g. atom, sublime, leafpad or notepad). Change some of the text in the project. Rembember to leave the HTML syntax intact.

run '''git status''' to see if something has changed and afterwards '''git add .''' and '''git commit'''. Run '''git status''' again to see if it worked.

## Create a remote branch and a pull request

For the next step, I need to add your github account to the repository.

run '''git branch''' if you don't remember the name of your branch.

run '''git push origin [your nickname-branch]. (Maybe github asks you to run some extra commands to set up your github credentials.)

if you are done, you can go to github and see your branch there. You can check out what changes you did and compare them to the previous version. You can also see the commits you did. If it looks good, click on "create a pull request". This means that I will get a message and I can merge your branch into the master branch. Congratulations, you are done with this workshop!


Final note: You don't need to know all of these commands by heart. Just google if you forget something, or check out a cheat sheet: https://services.github.com/on-demand/downloads/github-git-cheat-sheet.pdf

Some more things
================

## merge conflicts

Sometimes git will tell you, that it can not combine two files automatically. This is called a merge conflict. Go into the file where the conflicts occure and you will notice, that git added some notes. Basically it asks you, which of the two versions it should use from now on. Just choose the version you prefer and remove all the strange ====== and >>>>>>>>>>> that git added.

## github pages

This example repository contains a HTML website, because github offers an easy way to host such simple static websites. It is called "github pages". https://pages.github.com/
1. create a new repository named [your_github_username].github.io
2. Put an index.html file inside your project (like we did above)
3. Your website can now be found here: [your_github_username].github.io

## .gitignore

Sometimes you want git to ingore files or folders in your project. This is especially important, if you have passwords or API-keys in some file. Files or folders you mention in a ".gitignore" file will be ignored.

## markdown

You can write a readme.md for your project in a markdown-styled file, like this one. Github will show this readme on the main page of your project.








