# The Setup Document.
Linked from https://imlearningstuff.home.blog/2019/12/12/tooling-and-environment/

## Linux
Install Linux.  I'm using Mint.  
https://linuxmint.com/download.php

## Git
If you haven't already, create a github account, and a local git setup.

Download and install 
https://git-scm.com/downloads

Then;
```
$ cd <to the dir where you are keeping your local git workspace>
$ mkdir <your_workspace>
$ cd <your_workspace>
$ git init
$ git config --global user.name "Your name here"
$ git config --global user.email "your_email@example.com"
```

Then, create a new repo in github, and then check it out into your local git workspace
https://help.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository


## The Barebones Git Workflow
Run the below in your workspace directory.

1. check your git status
This shows the overll status of your workspace
```
$ git status
```

2. Add/Edit your files - Jupyter will create the files
Adds new file to your repo.

```
$ git add .
```


3. Commit your files locally
Saves your changes.  Git will ask you to enter some notes about the commit.
```
$ git commit .
```

4. Push your changes to master to github
Pushes your changes from local git workspace to master in github
```
$ git push origin master
```

This will ask for your user + password on github.  You can also add your username in the config file to save the step of entering the username.
Just add your username in the github link in the config file under the .git directory.

```
/repo/.git$ cat config 
[core]
	repositoryformatversion = 0
	filemode = true
	bare = false
	logallrefupdates = true
[submodule]
	active = .
[remote "origin"]
	url = https://agioskatastrof@github.com/agiosKatastrof/aiml.git
	fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
	remote = origin
	merge = refs/heads/master
```

## Jupyter, Python and a bunch of AI/ML libs via Anaconda
https://jupyter.org/install

But note the "We strongly recommend installing Python and Jupyter using the Anaconda Distribution, which includes Python, the Jupyter Notebook, and other commonly used packages for scientific computing and data science."

So that's what we're going to do. Install the Python 3.7 version.

https://www.anaconda.com/distribution/#download-section

## Running Jupyter
https://jupyter.readthedocs.io/en/latest/running.html#running

If the browser tab with the notebook doesn't launch automatically, click on the url link with the token.

Jupyter works in 'cells'.  You can run/save each cell independantly - but the latest state of the overall code is in memory - you need to be aware of what state your cell is in - see the number inside the [] brackets tells you the order of the cells in state.   

```
cntrl-s 
```
save cell

```
cntrl-enter 
```
runs snippet in cell


Where your started Jupyter is where your code will be, so you should start it in your local git repo directory.  But you can also browse via Jupyter's interface.  Jupyter files are .ipynb.

You are using Jupyter like an IDE.  After you save a notebook, commit and push the changes to github per above.
