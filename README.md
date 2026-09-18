# How to start a project using git

First install git by going to the following link and installing git using the matching OS type [git install](https://git-scm.com/install/).

Once you have install git make sure it is working by typing in the following in your terminal:

```Shell
git --version
```

# Setting up git config

For git you will need a username and an email for your commits. You can set them by running the following commands in terminal:

```Shell
git config --global user.name "MyUserName"
git config --global user.email "MyEmail@domain.com"
```

This information was gotten from github's knowledge base, if you would like more in depth information about github's user config please visit the [knowledge base](https://docs.github.com/en/get-started/git-basics/setting-your-username-in-git)

# Setting up SSH

The authentication method we are going to use is ssh for cloning repositories. First we need to create an ssh key.

Run the following in your terminal (Use the email address that you used to register with github):

```Shell
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Now that you have created an SSH key you will need to grab it.

There are a couple ways you have to get the key:

Linux/Mac

```Shell
cat ~/.ssh/id_ed25519.pub
```

On windows

```Shell
type ~/.ssh/id_ed25519.pub
```

Once you copy your ssh key you need to give these to github, you can do this by going to you profile in the top right > "settings" > "ssh and gpg keys" > "new ssh key" in the top right

Give the key a name and paste the key you got from id_ed25519.pub into the key field, then hit "add ssh key"

# Using git

Now that you have [installed git](#how-to-start-a-project-using-git), and you have [created an ssh key](#setting-up-ssh), You can use git with github.

First choose or create a new project in github.

Once you have a project you will need to be at the "project home page". If you are not sure where this is just hit "code" in the top left and it will take you there.

When you are on the main page, click the green "code" button that is just above the README and all of the repo files. You will see a small "clone" section with three options "**HTTPS**", "**SSH**", and "**Github CLI**", make sure **SSH** is selected. Now just press the copy button to the right of the ssh link.

Go to your terminal now:

We need to create a repo folder for all of the repos that we clone to live in:

This for example will create the folder on your desktop:

```Shell
mkdir ~/Desktop/gitrepo
```

next change to the directory you created, example below again
```Shell
cd ~/Desktop/gitrepo
```

Now let's clone our github repository using the ssh link from before
```Shell
git clone <your repo>
```

Now you can change directory into that repo
```Shell
cd <your repo>
```

## Git Commands

Now that you have successfully created and cloned a git repository you will need to use some git commands to work on it. The following will be a short run through of the process you will do for git and the commands you will need.

### Make Changes

The first thing you will do is make and save changes that you have done. Make a test file, create a python script, whatever you want to do.

### OPTIONAL Create a branch

If you are working in a repository with more than one person or some kind of production project where users and access a front end, it might be good to create branches, this way you can avoid awkward changes causing issues, or incoming changes causing problems when you write more code.

Creates and switches you to a new branch

```Shell
git checkout -b <branch_name>
```

Switch to a different branch

```Shell
git switch <branch_name>
```

### Stage Changes

After doing something with the repo we need to *stage* our changes this can be done with:

```Shell
git add <File or directory>
```

Or if you want to stage all of your changes:

```Shell
git add .
```

### Commit Changes

After staging your changes you need to *commit* your changes.

```Shell
git commit -m "Explain the work that you did for this commit."
```

### Pushing Changes

Once you have created a commit you can push your changes using:

```Shell
git push origin main
```

Or if you created a branch

```Shell
git push origin <branch_name>
```

### Pull and Merge Requests

If you have created another branch and pushed changes you will need to merge your pull request with main. If you are working on a bigger project there might be someone who approves merge request. A merge request will merge the incoming changes (changes you made) with the main branch (or whatever branches you are merging).

To do this go to "pull requests" in github > "new pull request", make sure your branch is selected and create the merge request.

Once you have created your merge request you can approve it