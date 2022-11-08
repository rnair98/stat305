---
title: SETUP.md
description: instructions for setting up dev environment
author: Rohit Nair
date: 11-08-2022
---

Install Git & GitHub
======================

## macos

Git is already installed on your system. Just download Homebrew and the GitHub cli.

1. Install Homebrew
`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

2. Install the GitHub CLI tool.
`brew install gh`

## windows

1. [Install WSL](https://learn.microsoft.com/en-us/windows/wsl/install-manual)

2. Once you're in your Ubuntu shell, follow the instructions under the `linux` section.

## linux

1. For Debian & Ubuntu based systems:
`curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg \
&& sudo chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg \
&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
&& sudo apt update \
&& sudo apt install gh -y`

2. For Arch-based systems:
`sudo pacman -S github-cli`

3. For Fedora, CentOS, and RHEL:
`sudo dnf install 'dnf-command(config-manager)'
sudo dnf config-manager --add-repo https://cli.github.com/packages/rpm/gh-cli.repo
sudo dnf install gh` 

Setup
=======

1. After downloading `gh`, you will need to login via your GitHub credentials. Run this command and follow the prompts.\
`gh auth login`

2. Next, navigate in your shell to your project directory and clone the project at `https://github.com/rnair98/stat305`\
`gh repo clone rnair98/stat305`
3. Next, go into the directory and switch to your branch.\
`cd cis427_project1`\
`git checkout ted` OR `git checkout abe`

Now you'll be able to work within your own branch and submit any changes you make to the code.

Git Workflow
=============

Everytime you introduce a change or series of changes to the codebase (editing `main.cpp` or adding new documentation), make sure to follow these steps.

1.`git add *`

2.`git commit -m "Insert message here about what you added/changed"`

3.`git push`

At the end, all of your changes will be synced to your development branch.

If you see that there have been changes to the main development branch, to pull these changes follow these steps:

1. `git checkout main`

2. `git pull`

3. `git checkout (Insert your branch name here)`

4. `git merge main`

5. `git push`

When you need to send in your code for review, that's when you submit a pull request.\
`gh pr create --fill --base main`

