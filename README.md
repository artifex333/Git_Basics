# FAQing Friday - Git Basics!

- [FAQing Friday - Git Basics!](#faqing-friday---git-basics)
  - [What is Git?](#what-is-git)
  - [Installing and configuring Git?](#installing-and-configuring-git)
    - [Installing Git](#installing-git)
    - [Configuring Git](#configuring-git)
  - [Choosing your management platforms.](#choosing-your-management-platforms)
    - [GitHub](#github)
    - [GitLab](#gitlab)
    - [BitBucket](#bitbucket)
  - [Basic Commands](#basic-commands)
    - [clone](#clone)
    - [fork](#fork)
      - [add](#add)
      - [commit](#commit)
    - [push](#push)
    - [pull](#pull)
    - [branch](#branch)
      - [Pull Requests (GitHub)](#pull-requests-github)
  - [Gitignore File](#gitignore-file)

## What is Git?

![Git_Meme](https://www.memecreator.org/static/images/memes/5482008.jpg)

It's all about version control! Essentially, Git is a light weight, free, open source version control tool used in small and projects to house code for developers to interact with each other. In other words, you can think of Git as a database that devs use to store, ship, and collaborate with other devs on their code.

The next question you may be asking is what the hell is version control?? Version control, or source control, is the practice of tracking and managing changes to software code. So, let's say that you and Rob are working on a new malware to hack Will's computer (Sketchy business...), and he commits changes. You can then pull his changes from the repository to your computer, thus creating a new version of the malware.

---

## Installing and configuring Git?

### Installing Git

Just like most things, Linux, Mac, and Windows installation will differ.

 - Linux - Git comes preinstalled. However, if it is not preinstalled, you can install with ```sudo apt update``` and then ```sudo apt install git-all``` on Debian/Ubuntu. If you are using another linux distro consult that distro's documentation for installing packages.
   - To check your version run: ```git --version```
 - Mac - Git comes preinstalled.  However, if it is not preinstalled, you can install with this [macOS Git Installer](https://sourceforge.net/projects/git-osx-installer/files/git-2.23.0-intel-universal-mavericks.dmg/download?use_mirror=autoselect) or install with Homebrew using this command ```brew install git```. If you do not have brew installed, follow the [Installing Hombrew Documentation](https://docs.brew.sh/Installation)
   -  To check your version run: ```git --version```
 - Windows - Git on Windows requires you to use the [Git for Windows](https://gitforwindows.org/)
   - After downloading and installing, open a terminal or "Git Bash" and run: ```git --version```

### Configuring Git

Configuring your Git will all be done in the CLI.

- To list all of your settings:
  - ```git config --list --show-origin```
- To set your user name:
  - ```git config --global user.name "John Doe"```
- To set your email:
  - ```git config --global user.email johndoe@example.com```
- Your user name and email need to match the user name and email you use to sign into your Git management platform (ie. GitHub).

---
## Choosing your management platforms.

### GitHub

- [GitHub](https://github.com) is a free (for the most part) management platform that allows you to create public and private repositories. It's the most popular management platform. It's the one I started on and used as my daily driver.

### GitLab

- [GitLab](https://gitlab.com) is also free, however it's more geared toward large organizations that rely on advanced DevOps practices using CI/CD pipelines.

### BitBucket

- [BitBucket](https://bitbucket.org) is owned by Atlassian and is designed for organizations who are integrated with Atlassian's products (Jira, Confluence, etc.).

---

## Basic Commands

![git_fire](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQSqFsPoKOTiNiamjS9CRpI1BadKwhK-EqGSU2kq8vPuTuejN6RMpcfMDAx5QHn9u_j8Dk&usqp=CAU)

You will be interacting with Git through the CLI at first. Once you understand what the commands are doing, then I'll show you how you can do the same process in VSCode. Below is a useful list of common Git commands you will use.

**Note** This process can done in another IDE, however I use VSCode.

### clone

- The clone command allows you to clone a repository to your machine. It clones all of the documents and code inside the repo, and allows you pull changes and create pull requests when you push to the repository. Cloning a repo will create a directory for that repo in the current path you are in.
  - ```git clone https://github.com/repo_name/repo_name```


### fork

- The fork command is similar to clone. Forking a repo provides complete control over the codebase. Essentially, you are taking a snap shot of the repo at that time and working off of the codebase. 
- Unlike cloning where devs can pull and push changes, a forked repo is a new repo with the source code and you and whoever you allow can make changes.
  - You can fork a repo on your version control management platform through the WebUI. You can also use GitHub's CLI with: ```gh repo fork https://github.com/repo_url```

#### add

- After saving and testing your changes, you're ready to push your new code to your repo. For a push to be made it starts with the "add" command.
- The add command tells git exactly what you want to add to your push. Pretty simple, right?!
  - Git status shows which files in the repo that has been modified: ```git status```
  - You can add one or multiple files with ```git add /path/to/file```
  - Or you can all the modified files with ```git add .```
  - If you run a Git status again, you should see all of your files have been added.

#### commit

- After adding your files, you now have to commit the changes. It's pretty simple, you tell the CLI you want to commit the modified files you added, and write a short commit message to be store in the Repo.
- Make sure your messages are short but describe what's in the commit.
  - ```git commit -m "Your commit message goes here!"```

### push

- Now that you have added and committed your files, you're ready to push your changes to your repo! Hell yeah!
- Now all you have to is run ```git push <remote> <branch>``` to push your changes.
- Most of the time it will look like this ```git push origin main``` because you are pushing to the main branch. 

### pull

- The pull command does exactly what it says it's doing. It's pulling any changes to the repo that have been made since the last time you pulled the repo. 
- **NOTE** It's a good idea to run the pull command before creating any branches so you can work on the latest version of the code base.
  - ```git pull``` (**NOTE** You must be inside the repo's directory for this to take place...)
### branch

- Creating branches are a super important process to Git and to the development cycle. Branches are pretty much little snapshots of the repo's code base so that you can make changes to without editing or breaking code on the main branch.
- Branches are used for creating one off features to test before merging into the main branch.  We do this so new code doesn't break the current version of the code base. 
- **NOTE** This [article](https://www.atlassian.com/git/tutorials/using-branches) is an awesome tutorial on creating and using branches.
  - To view the current branches you have: ```git branch -a```
  - To create a new branch: ```git branch <branch_name>```
  - To delete a branch: ```git branch -d <branch_name>```
  - To force delete a branch: ```git branch -D <branch_name>``` (This command is a little sketchy...)
  - To rename a branch: ```git branch -m <branch_name>```
  - To switch to a different branch: ```git checkout <branch_name>```

#### Pull Requests (GitHub)

- Okay, thanks for hanging in there! Now that you have created a branch, modified some files with your badass code, added, committed, and pushed your badass code to your branch, you have to now create a pull request for your code to be merged from your current branch into your main branch. Thankfully, GitHub does all of this for you in the UI. It's pretty simple.
- In your GitHub repo, click pull request
- You want to make sure you are merging from the branch where you made the changes to the main branch
- Write up a message, add a reviewer, and click create pull request.
- If this is your personal repo, you can view the PR and merge it yourself. If you are working with a team, get someone else to review your code prior to merging. That way there are a fresh set of eyes looking at the code.


---
## Gitignore File

- The Git Ignore File is another super important piece. Essentially, anything added to the ".gitignore" file Git will ignore it when looking for modified files and otherwise will not add those files to the repo.
- To create a .gitignore file, inside the repo's directory: ```touch .gitignore```
- Then you vim, nano, or VSCode your ignored files.

---

This is the just the tip of the iceberg when it comes to Git. It's an amazing tool that the tech world cannot live without. If you like this, checkout jobs in the GitOps space. It's a newish field that is popping up that's all about to build a culture around the best Git practices using CI/CD process.