---
layout: page
title: Python
parent: Tutorials
nav_order: 3
---

# Python and Jupyter

We're now going to attempt to install Jupyter and additional Python libraries in a controlled, virtual environment. If you have installed Anaconda in the past then you may want to disable it to avoid any conflicts, or if you're comfortable with Anaconda, use it to install Jupyter and python-related libraries. 
If you don't know what Anaconda is you can look it up in your own time but for the purposes of this tutorial, I won't mention it again.

{: .note }
> Don't forget: If you run into any difficulties during this install process, please post in our class channel (**#phys709-fall2024**) on Slack.

There's a multitude of resources online for your specific system, but the installation instructions herein should suffice for the most generic install. For the record, they worked for me on an Ubuntu-based zsh-shell via [Windows Subsystem for Linux (WSL)](https://ubuntu.com/desktop/wsl); allows one to access Ubuntu (Linux) terminal environment on Windows.

## Prequisite

- python v3+ (my setup has python v3.10.12)

Ubuntu 22.04 comes with Python 3.10 installed. To check what version of python you have installed on your system:

```zsh
python3 -V
```
or
```bash
python3 --version
```
If Python is not on your machine then you're going to need to install it (and make sure your machine is up-to-date):
```zsh
sudo apt update && upgrade
sudo apt install python3
```
If you're using a Mac, I suggest using [homebrew](https://brew.sh/).

## Install pip

Alright, so we're going to want to also install `pip` (not installed by default on Ubuntu for example):
```zsh
sudo apt install python3-pip
```
This will install several various packages/dependencies for pip.

{: .note }
> What is `pip` you may ask...It is the package installer for python which will allow us to install python applications/libraries and their dependencies. Pip allows you to install and manage additional packages that are not part of the Python standard library. 

## Install venv

With pip installed, we can now create a virtual environment (`venv`). This will allow us to install additional python applications in a stable, reproducible environment. It puts you in control of the version of packages and when they get upgraded. Essentially keeping our work here separate from the main environment -- so we can be safe in the knowledge that if we make mistakes, break things, we can delete the virtual environment and start again easily.
Install `venv`:
```zsh
sudo apt install python3-venv
```

We're ready to create our first virtual environment now. You're going to want to create this in a directory that makes sense to you. 
I have all of my virtual environments installed in `~/venvs`
```zsh
# change directory to our $HOME i.e `~`
cd $HOME
# tells you what the environment variable $HOME points to
echo $HOME 
# verify where we are
pwd
# make a directory called venvs
mkdir venvs
 # make a virtual environment called .my-venv
python3 -m venv .my-venv
```

{: .warning }
> .my-venv is installed as a hidden folder.
> You'd need to type `ls -a` to see any hidden folders.
> That's a personal choice I made. You don't need the `.` and can also call it whatever you like.

We can now activate our virtual environemnt. Pay attention now, this command you'll run every time you want to do any work in your virtual environment.
```zsh
source ~/venvs/.my-venv/bin/activate
```

When you are finished working in your venv, you should deactivate it, simply:
```zsh
deactivate
```

## Install Jupyter

```zsh
sudo apt install ipython3 jupyter-core
```
We should be ready to install Jupyter now, where your terminal (in my case, WSL) will act as a jupyter server accessible to view on a browser at localhost through port 4000. Let's install jupyter:
```zsh
pip3 install jupyter
```

Assuming everything went well, we should be able to launch jupyter now:
```zsh
jupyter notebook
```
If this opens jupyter in a browser then we are ready for the next stage!

You can proceed to the [Python II]({{ site.baseurl }}{% link tutorials/python2.md %}) page.

{: .note-optional }
> Now I prefer for jupyter to not launch automatically in a browser (because I want to open it in Chrome and not the WSL default browser) so I add an alias to redirect it. Since I use `oh-my-zsh` to manage my `zsh` configuration, I use my favorite editor (`vscode`) to open `$ZSH_CUSTOM/aliases.zsh`, but for most use cases you can just open your `~/.bashrc` file. Open one of these files and add the following:
```zsh
alias jupyter-notebook="~/.local/bin/jupyter-notebook --no-browser"
```
Save and close your editor and then either re-source your shell config file or start a new terminal, reactivate your venv if needed and launch jupyter notebook, e.g.:
```zsh
source ~/.bashrc
jupyter notebook
```
