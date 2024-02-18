# Using Git - GitHub

## 1.1 Creating the repository

Using your GitHub account, create a repository to which you can add files. Name the repository as MyFirst. Create a public repository and check the box to create a README file.
You can clone the repository you created with `git clone <URL>` command. This copies the repository from a remote machine and initializes it on your machine.
After you create the repository, the URL of your web page would be something like https://github.com/USERNAME/MyFirst. Replace USERNAME with your username.
You can also try to clone any public repositories on github.com

## 1.2 add and commit
```
#You can propose changes (add it to the Index) using
$git add <filename>
#This is the first step in the basic git workflow.

#To see changed and added files
$git status

#To actually commit these changes use
$git commit -m "Commit message"
```

## 1.3 Pushing changes
```
$git push
```

## 2.1 Initializing repository locally 

The other way is initializing git repository locally. 
```
Create a new directory in your home directory or any other suitable location using
$mkdir hello-world
Enter it
$cd hello-world
and create a new git repository using 
$git init
```

## 2.2 Configure your email and username of Github in the git
```
$git config --global user.email "username@email.com"
$git config --global user.name "username"
```

## 2.3 add and commit (Same as 1.2)
```
#You can propose changes (add it to the Index) using
$git add <filename>
#This is the first step in the basic git workflow.

#To see changed and added files
$git status

#To actually commit these changes use
$git commit -m "Commit message"
```

## 2.4 Pushing changes 
```
#If you have not cloned an existing repository and want to connect your repository to a remote server, you need to add it with

$git remote add origin https://github.com/USERNAME/REPOSITORY.git 
Replace the URL with the repository you made before

Now you are able to push your changes to the selected remote server i.e. your remote repository on GitHub.
Your changes are now in the HEAD of your local working copy. To send those changes to your remote repository, execute 
$git push -u origin master
```
# Troubleshooting
You could encounter errors if you do not follow the exact procedure as described above.
```
error: failed to push some refs to 'git@github.com:myrepo.git'

Solution:

$ git pull origin master
```

```
fatal: refusing to merge unrelated histories

Solution:

$ git pull --allow-unrelated-histories origin master
```


# Branches

## Why Branches ?
To expand.
Trees need branches to expand. 
Banks needs (office) branches to expand.
Company needs (code) branches to expand.
E.g. Branches for Bugs, testing, featuers, production, staging etc. 

## What is a branch ?
Branch is a name given to the commit. Internally, it is pointer to the commit object.
By default, this name/pointer is **master**. Every time you make a new commit, this pointer moves forward.
When you create a new branch, new name/pointer is created to point to the current commit.
How does Git know which branch you are currently one ? It keeps a special pointer called **HEAD**.

## Checkout

    The git checkout command lets you navigate between the branches created by git branch.
    Checking out a branch updates the files in the working directory to match the version stored in that branch,
    and it tells Git to record all new commits on that branch. Think of it as a way to select which line of 
    development you’re working on.

To check out the specified branch, which should have already been created with git branch, run:
`git checkout <existing-branch>`
This makes <existing-branch> the current branch, and updates the working directory to match.

To create and check out <new-branch>, run
`git checkout -b <new-branch>`
    The -b option is a convenience flag that tells Git to run git branch <new-branch> before running git checkout <new-branch>.
  
  # Pull requests: 
Pull requests make it easier for developers to collaborate. They provide a user-friendly (web) interface for discussing
proposed changes before integrating them into the official project.
In the simplest form, pull requests are means for a developer to notify a team member that they have completed a feature. But the pull-request is more than just a notification. It's a dedicated forum where teammates can post feedback, push follow-up commits.

## 1. What does a pull request contain:
When you create a pull request, you want another developer to pull a branch from your repository into their repository. This means that you need to
provide 4 pieces of information to create a pull request:
* the source repository
* the source branch
* the destination repository
* the destination branch

Pull requests can be used in conjunction with various workflows:
* Feature-branch workflow
* Gitflow workflow
* Forking workflow

# 2. Forking Workflow
In the Forking workflow, a developer pushes a completed feature to their own public repository instad of a shared one.
After that, they create a pull request to let the project maintainer know that it's ready for review.

Since each developer has their own public repository, the pull request's source repository will differ from its destination repository.
The source repository is the developer's public repository and the source branch is the one that contains the proposed changes.
If the developer is trying to merge the feature into the main codebase, then the destination repository is the official project and 
the destination branch is "master".

Steps in Forking Workflow:
* You fork a public repository
* You clone the repository (so that you have a working copy on your machine)
* You create a (feature) branch and make some commits
* You push the branch in your repository
* You create a pull request by navigating to your forked repository

this line is added via other branch