# FAQing Friday - Git Basics!

- [FAQing Friday - Git Basics!](#faqing-friday---git-basics)
  - [What is Git?](#what-is-git)
  - [Installing and configuring Git?](#installing-and-configuring-git)
    - [Installing Git](#installing-git)
    - [Configuring Git](#configuring-git)
  - [Choosing your managment platforms.](#choosing-your-managment-platforms)
    - [GitHub](#github)
    - [GitLab](#gitlab)
    - [BitBucket](#bitbucket)
  - [Basic Commands](#basic-commands)
    - [clone](#clone)
    - [fork](#fork)
    - [pull](#pull)
    - [push](#push)
      - [add](#add)
      - [commit](#commit)
    - [branch](#branch)
      - [Pull Requests vs Merge Requests](#pull-requests-vs-merge-requests)
  - [Gitignore File](#gitignore-file)

## What is Git?

It's all about version control! Essentially, Git is a light weight, free, open source version control tool used in small and projects to house code for developers to interact with each other. In other words, you can think of Git as a database that devs use to store, ship, and colloaborate with other devs on their code.

The next question you may be asking is what the hell is version control?? Version control, or source control, is the practice of tracking and managing changes to software code. So, let's say that you and Rob are working on a new malware to hack Will's computer (Sketchy business...), and he commits changes. You can then pull his changes from the repoisotry to your computer, thus creating a new version of the malware.

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
## Choosing your managment platforms.

### GitHub

- [GitHub](https://github.com) is a free (for the most part) management platform that allows you to create public and private repositorties. It's the most popular management platform. It's the one I started on and used as my daily driver.

### GitLab

- [GitLab](https://gitlab.com) is also free, however it's more geared toward large organizations that rely on advanced DevOps practices using CI/CD pipelines.

### BitBucket

- [BitBucket](https://bitbucket.org) is owned by Atlassian and is designed for organizations who are integrated with Atlassian's products (Jira, Confluence, etc.). 

---

## Basic Commands

You will be interacting with Git through the CLI at first. Once you understand what the commands are doing, then I'll show you how you can do the same process in VSCode. Below is a useful list of common Git commands you will use.

**Note** This process can done in another IDE, however I use VSCode.

### clone

- The clone command allows you to clone a repoistory to your machine. It clones all of the documents and code inside the repo, and allows you pull changes and create pull requests when you push to the repository. Cloning a repo will create a directory for that repo in the current path you are in.
  - ```git clone https://github.com/repo_name/repo_name```


### fork

- The fork command is similar to clone. Forking a repo provides complete control over the codebase. Essentially, you are taking a snap shot of the repo at that time and working off of the codebase. Unlike cloning where devs 
### pull
### push
#### add
#### commit
### branch
#### Pull Requests vs Merge Requests

---
## Gitignore File

---