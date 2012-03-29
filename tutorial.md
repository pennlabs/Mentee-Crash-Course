# A Simplified PennCourseReview

## Primary Objective: Build a simplified version of PCR.
**Description**: Welcome to PennApps Labs! We’re excited to to begin working with you! Before we get started though, it’s helpful if we can get you up to speed on the tools that we use and the environment that we work in. To that end, we’ll be guiding you through building your own simplified version of PennCourseReview. If at anytime you get stuck, feel free to personally email the author, Ceasar Bautista, at cbautista2010@gmail.com or anyone else on the team. 

With that, let’s begin.

## Working on your Local Machine
_Getting stuff working on your local machine is optional, but can be useful. You can skip this section if you’d rather dive straight into the assignment._

### Objective: Install Python
**Description**: Your first objective is to install Python. Python is a general-purpose, high level programming language whose design philosophy emphasizes code readability. Python supports multiple programming paradigms, primarily, but not limited to, object-oriented, imperative, and to a lesser extent, functional programming styles. It features a fully a dynamic type system and automatic memory management.

**Instructions**: If you’re using Linux or Mac OS X you should already have Python installed. Otherwise, simply go to http://www.python.org/download/ and follow the instructions as directed.

**Notes**

- To verify Python is installed simply type `python` into your shell to start the Python interpreter. (Type `quit()` to exit.)

### Optional Objective: Install `pip`
**Description**: `pip` is a tool for installing and managing Python packages. It’s generally useful for personal use, but it also makes install Django super easy.

**Instructions**: You can download pip by following the instructions at: http://www.pip-installer.org/en/latest/installing.html.

### Objective: Instal virtualenv
**TODO**

### Objective: Install Django
**Description**: Django (pronounced “Jango”) is an open source web application framework, written in Python, which follows the model-view-controller architectural pattern. It was originally developed to manage several news-oriented sites and has since become a standard for web development in Python. Django’s primary goal is to ease the creation of complex, database-driven websites, emphasizing reusability, and rapid development.

**Instructions**: If you previously installed `pip`, you can install Django by typing `sudo pip install django` into your terminal. Otherwise, you can download Django at: https://www.djangoproject.com/download/.

**Notes**:

- To verify you have Django installed, open up the Python interpreter and type `import django` followed by `print django.get_version()`.
- Notice that when typing `sudo pip install django` you were prompted for your password. The `sudo` command gives you permission to do anything, and to ensure other people don’t ruin your machine, `sudo` needs to verify you have permission.


### Objective: Download Vim
**Description**: Vim is a highly configurable text editor built to enable efficient text editing. It is an improved version of the vi editor distributed with most UNIX systems. Vim is often called a "programmer's editor," and is so useful for programming that many consider it an entire IDE. It's not just for programmers, though. Vim is perfect for all kinds of text editing, from composing email to editing configuration files.
**Instructions**: Go to http://www.vim.org/download.php and download Vim.
**Notes**: Vim is not the only text-editor out there. While Vim is an excellent default, and many people at Labs use it, many also use Emacs. You're encouraged to take both for a ride and see what fits your needs.


## Getting Familiar with the Environment

### Primary Objective: Create an html file to use as the index of PCR.

#### Objective: ssh into the server.
**Description**: Secure Shell (`ssh`) lets you log in to other computers and sets up a secure connection for you to use as if the computer were your own. Before we start anything we’ll need to ssh in.
**Instructions**:
If you’re using a Mac or Linux machine, find and open Terminal and then type `ssh username@pennapps.com` to access our servers. If you’re on Windows, download PuTTY and read the instructions to connect into our server.
**Objective**: Create an html file to use as the index of PCR.

**Description**: Welcome to our server. You’ll notice ssh has no GUI — instead you’ll have to pick up UNIX to get around. While we’re at it, let’s create our future index page.
**Instructions**:

- First type `ls` (short for “list”) to see what files are in the current directory you’re in.
- Next, type `touch index.html` to create our future index page.
- Now type `mkdir media` (short for “make directory”) to make a new directory called `media`. - Type `ls` again to see the two files we just created.
- You can use `mv filename newfilename` (short for “move”) to rename a file. You can also move files by putting a directory before the name. Let’s move our index.html file into media now typing `mv index.html media/index.html`. Type `ls` and then `ls media` to confirm we moved the file.
- Next type `cd media` (short for “change directory”) to move into media. To go back (or “up”) type `cd ..` (two periods)
- Type `vim index.html` to open the file using vim.

**Notes**:

- Type `man <command>` to open the manual for a command.
- To delete files, use `rm`. (Be aware that `rm` deletes a file permanently, so be careful.)
- To delete empty directories, use `rmdir`. To delete non-empty directories use `rm -r`. (“-r” stands for “recurse”) 
- If you get lost in the maze of directories, type `cd ~` to navigate back to your home directory. You can also use `pwd` to see your current directory path. Try doing that now.
- As you’ll notice, typing out directory names is a bit inefficient. Fortunately, you can autocomplete using Tab. (If it doesn’t work the first time, press Tab again to display the possible completions.)
- Also, you should be aware that you can use the up and down arrows to go through the history of previously typed commands. You can also use CTRL-p and CTRL-n, they way you would in Emacs.

#### Objective: Edit index.html and make it pretty.
**Description**: When we created index.html, it created a completely empty file for us. While it’s not important that it’s pretty, we should have some content on the page.

**Instructions**:

- We’re going to use Vim to edit the file. Vim is a advanced text editor used by many programmers, including us at Labs. Type `vim index.html` to start editing.
- Don’t type anything yet! Vim is very complicated, but powerful once you get to know it. For now we’ll just use it basically. Type `i` to go into Insert Mode.
- At this point you can type freely. Try typing some characters now to get started.
` To move the cursor, you’ll need need to exit Insert Mode and return to Normal Mode. Press `Esc` to go back to Normal Mode and then use `h, j, k, l` to move around. (h=left, j=down, k=up, l=right). It’ll feel a little clunky at the moment, but you’ll get used to it.
- When you’re done type `Shift+ZZ` to save and quit.
- At this point you should actually make index look reasonable. Just put a header, a short description of what pcr is, and a link to the actual penncoursereview.com.

**Notes**:
- You’ll probably want to learn the other commands of Vim. Just google around or type `vimtutor` into the terminal for help.
- Don’t worry about css. It’s useful to know, but not important for this assignment.
- To view your index page, copy over into your `public_html` folder. You can then view the file by visiting pennapps.com/your_username.

## Creating a Django Project & using Git

### Objective: Start a Django project.
**Description**: With Django installed, we can get started putting together a project.

**Instructions**:

- Navigate back to the root (`cd ~`) and enter `django-admin.py startproject pcrsite`. This will create a folder called `pcrsite`.
- Now, move the `media` folder we created earlier into the project. We’ll be using it shortly.
At this point someone will either have set up Apache or you may need to email them to check out what we just created.

**Notes**:

- A Django project at its core consists of four parts.
	- `__init__.py` denotes that the project is a Python project.
	- `manage.py` is pretty much a giant script. It has a lot of powerful commands used to manage a project.
	- `settings.py`, as expected, contains a bunch of settings for the project. We will be changing this up shortly.
	- `urls.py` is used to map URLs to content