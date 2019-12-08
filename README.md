# aiml 
learning AI/ML

## I. TOOLING

### Anaconda
Anaconda is a packaged suite of tools related to machine learning.  
It comes with a distribution of python and AI/ML libs
https://anaconda.com
https://www.anaconda.com/distribution/#download-section
You can use any OS, but Linux seems best.  The below directions will be for Linux (Mint).

### Jupyter
Jupyter can be used outside anaconda, but anaconda  includes jupyter
https://jupyter.org/

Jupyter is browser based tool for experimental coding.   It is not meant for creating apps, but helps to code ad-hoc, as you think - a notebook, per se.  It is often used in machine learning, but can be used in general when testing out snippets of code.

Jupyter works in 'cells'.  You can run/save each cell independantly - but the latest state of the overall code is in memory - you need to be aware of what state your cell is in - see the number inside the [] brackets tells you the order of the cells in state.   

```
cntrl-s 
```
save cell

```
cntrl-enter 
```
runs snippet in cell

### IDE
You don't actually have to use Jupyter, as you can write/code directly in Jupyter.
Jupyter however, does not have Source Version Control - so you may want to have an IDE;

If you choose to use an IDE, you can use pycharm (for linux mint below)
https://linux4one.com/how-to-install-pycharm-on-linux-mint-19/

### GIT
Or you can just use Jupyter + command line git.


To setup a git client
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


The barebones git workflow.
Run the below in your workspace directory.

1. check your git status
This shows the overll status of your workspace
```
$ git status
```

2. Add/Edit your files - Jupyter will create the files
adds new file to your repo

```
$ git add .
```


3. Commit your files locally
saves your changes
```
$ git commit .
```

4. Push your changes to master to github
pushes your changes from local git workspace to master in github
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


### Using Jupyter

launch jupyter from command line
```
$ cd <your_workspace>
$ jupyter notebook
````
The above will follow with a bunch of logs - open the link with the http://localhost or http://127.0.0.1 with the token

click 'new' upper right to start a new file - choose python3

## II. THEORY

### SCIKIT
use scikit, one of the more commont ML libs
it is included in the Anaconda package
https://scikit-learn.org/stable

Note that using Jupyter, you need not "print".  The stdout (standard out) will be displayed in the browser.

#### SVM
Start with  SVM (support vector machine) example
At a high level SVM helps you to categorize data - as simple as a Yes/No, based on previous known sample data.
E.g.,

1. Takes in test data composing of fruits and vegetables.
2. Then given a fruit (say, Apple), the SVM will try to determine if it is a fruit or a vegetable, based on the data it has (the data that it has been "trained" with).

The below has nice graphical illustration of SVM
Go through the theory explanations, and then follow through on the examples beginning with "Loading Data"
https://www.datacamp.com/community/tutorials/svm-classification-scikit-learn-python

Questions to ask yourself -
1. What are "features" of a data set?
https://www.datarobot.com/wiki/feature/
Essentially, columns of a table

2. What is "shape"?
https://docs.scipy.org/doc/numpy/reference/generated/numpy.ndarray.shape.html
Describes the array with respect to its row, column lengths

3. What is the "target"?
https://datascience.stackexchange.com/questions/44108/difference-between-a-target-and-a-label-in-machine-learning
Essentially, the output that you are trying to determine

https://stackabuse.com/implementing-svm-and-kernel-svm-with-pythons-scikit-learn

https://stats.stackexchange.com/questions/155146/visualizing-svm-results
