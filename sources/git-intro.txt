Git and Github
==============

An Introduction

What We'll Cover
----------------

* What's Git
* Using ``git``
* More resources

First Things First
------------------

* `Make an account on github <https://github.com/join>`_

Why Bother?
-----------

.. figure:: /static/phd_final.gif
    :height: 500px
    :align: right

Image from
`PhD Comics <http://www.phdcomics.com/comics/archive.php?comicid=1531>`_

Better Options: Version Control
-------------------------------

* Commit = Snapshot of part of your project's state
* Centralized (SVN, CVS) vs. Decentralized (Git, hg)
* We'll look at Git today
    * Easier to learn other VCS from Git
    * Widely used in the open source world

Git
---

.. figure:: /static/Linus_Torvalds.jpeg
    :height: 400px
    :align: left

git, noun. Brit.informal.
1. an unpleasant or contemptible person.

Setting up Git
--------------

* Linux:

.. code-block:: bash

    $ sudo [yum | apt ]  install git

* Windows & Mac: https://desktop.github.com/

Configs
-------

[user]
    email = wyman.lucy@gmail.com
    name = Lucy Wyman

[core]
    editor = vim

[credential]
    username = lucywyman

Using Git Locally
-----------------

.. code-block:: bash

    $ git init
    # Make your changes
    $ git status # or git diff
    $ git add <filename>
    $ git commit 
    $ git push origin <branchname>

* Undo things?
  the `git book <http://git-scm.com/book/en/Git-Basics-Undoing-Things>`_ explains
  well
* What commits have I made lately?

.. code-block:: none

    $ git log

What Not To Do
--------------

* **Don't delete the .git files**
* Avoid redundant copies of the same work in one revision
* Don't make "oops, undoing that" commits.
    * Use git commit --amend or git revert
* Don't wait too long between commits
    * You can squash them all together later
* Don't commit secrets, and if you do **change them**. Git never forgets.

http://arstechnica.com/security/2013/01/psa-dont-upload-your-important-passwords-to-github/

Git Exercise
------------

First create a git repository!

.. code-block:: none

    $ mkdir my_python_app
    $ cd my_python_app
    $ git init

Git will do a one-time prompt for some basic information and then you have a
Git Repository! All code in this code can be tracked by git as a single
project.

Adding Code
-----------

Create and open a new file ``script.py`` with the following command:

.. code-block:: python

    def f(x):
        print(x**x)
    if __name__ ==  "__main__":
        f(5)

Save this file and leave the text editor and tell git to track this code.

.. code-block:: none

    $ git status
    $ git add script.py
    $ git commit -m "My first git commit!"
    $ git status
    $ git push origin master
    $ git log

Cloning a Repository
--------------------

Git also allows you to ``clone`` a remote repository to work on another
person's code. It's like downloading the entire project and it's git history.

.. code-block:: none

    $ cd ~
    $ git clone git@github.com:DevOpsBootcamp/tinsy-flask-app.git
    $ cd tinsy-flask-app
    $ ls

You have successfully clone a remote repository and can start modifying the
other person's code. Changes you make on your local version of this project
will not affect the original version you modified (although you can push
changes if you are allowed to do so by the original owner!)

Branches
--------

Github allows you to 'branch' your codebase. This allows you to make changes
on a separate track without modifying the original codebse in the same
repository. Branches are preserved when you clone a remote repository.

.. code-block:: none

    $ git checkout broken
    $ python myapp.py

Now you can see your webapp doesn't work correctly when you try to access it in
the browser!

We can manually go in and fix it, or run a command to see what changed between
this version and the version in the 'master' branch.

.. code-block:: none

    $ git diff master

Daily workflow
--------------

.. figure:: /static/gitflow.png
    :height: 400px
    :align: right

Pull -> Work -> Add changes -> Commit -> Push

Larger projects have more complex workflows

GitHub!
-------

.. figure:: /static/octocat.jpg

* Free online code storage
* Easily share and collaborate on code
* Great Git documentation
* Easily findable source-code

Other Resources
---------------

* `Github Documentation <https://help.github.com>`_
* `Git Visualizations <http://www.wei-wang.com/ExplainGitWithD3/#>`_
* `Further tiny-flask-app exercises <https://github.com/DevOpsBootcamp/tinsy-flask-app#now-what>`_

