---
layout: page
title: Version Control II
parent: Tutorials
nav_order: 2
---

# Python and Jupyter

We're now going to attempt to install Jupyter and additional Python libraries in a controlled, virtual environment. If you have installed Anaconda in the past then you may want to disable it to avoid any conflicts, or if you're comfortable with Anaconda, use it to install Jupyter and python-related libraries. 
If you don't know what Anaconda is you can look it up in your own time but for the purposes of this tutorial, I won't mention it again.

{: .note }
> Note
>
> Don't forget: If you run into any difficulties during this install process, please post in our class channel (#phys709-fall2024) on Slack.

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
If Python is not on your machine then you're going to need to install it:
```zsh
sudo apt update && sudo apt install python3
```
If you're using a Mac, I suggest using [homebrew](https://brew.sh/).
Alright, so we're going to want to also install `pip` (not installed by default on Ubuntu for example):
```zsh
sudo apt install python3-pip
```
This will install several various packages/dependencies for pip.

{: .note }
> FYI
>
> What is `pip` you may ask...It is the package installer for python which will allow us to install python applications/libraries and their dependencies. Pip allows you to install and manage additional packages that are not part of the Python standard library. 

With pip installed, we can now create a virtual environment (`venv`). This will allow us to install additional python applications in a stable, reproducible environment. It puts you in control of the version of packages and when they get upgraded. Essentially keeping our work here separate from the main environment -- so we can be safe in the knowledge that if we make mistakes, break things, we can delete the virtual environment and start again easily.
Install `venv`:
```zsh
sudo apt install python3-venv
```

We're ready to create our first virtual environment now. You're going to want to create this in a directory that makes sense to you. 
I have all of my virtual environments installed in `~/venvs`
```zsh
cd $HOME # change directory to our $HOME i.e `~`
echo $HOME # tells you what the environment variable $HOME points to
pwd # verify where we are
mkdir venvs # make a directory called venvs
python3 -m venv .my-venv # make a virtual environment called .my-venv
```

{: .warning }
> .my-venv is installed as a hidden folder.
> That's a personal choice I made. You don't need the `.` and can also call it whatever you like.





<!--{% highlight Code %}
some code
{% endhighlight %}-->

<!--{: .highlight } 
> Code
>
> python3 -V
{: .source}-->

Rather than reinvent the wheel, we'll make use of the excellent resources provided by [Software Carpentry](https://software-carpentry.org/).
Specifically your task is to follow the Software Carpentry tutorial [Version Control with Git](https://swcarpentry.github.io/git-novice/).
I honestly believe this is more fun than it is onerous "homework". Have fun with it, explore, collaborate, learn!

If you're not comfortable with the Unix Shell, I can recommend Software Carpentry's [The Unix Shell](https://swcarpentry.github.io/shell-novice/) tutorial; recommended not required.

Of course, you already have a GitHub account so you should be able to dive straight into this tutorial. You'll also quickly learn that you want to use a good text editor.
My personal favorite at the moment is [VS Code](https://code.visualstudio.com/) which has really nice integration with Git, but this is a very personal choice (of which there are many).
I'm happy to show you my personal setup Windows+WSL+ohmyzsh+vscode upon request.

Recall how you all made `test-repo` in the earlier tutorial. Well, when you get to part [3. Creating a repository](https://swcarpentry.github.io/git-novice/03-create.html),  you can repurpose your `test-repo` by [renaming your repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/renaming-a-repository) to the suggested `planets` and then continue following the tutorial; that way I should maintain my access.

When you get to part [8. Collaborating](https://swcarpentry.github.io/git-novice/08-collab.html), where it says get into pairs, find one or more classmates to collaborate with and follow the instructions for sharing and collaborating with each other's repositories. I'll be able to verify this (and aid with any conflicts) by observing commits within all the repositories.

If you want to go beyond, explore at your own pace [Advanced git](https://learngitbranching.js.org/?locale=en_US) with an interactive webpage that helps one learn how to work with branches.
