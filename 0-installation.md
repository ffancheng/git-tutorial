---
layout: page
permalink: installation/
title: Installation and setup
---

To work with this tutorial, you're going to need a few things:

- **Git**, of course. Install this by going to the git homepage,
  [git-scm.com](http://git-scm.com) Or see next section. 
- **A text editor**. Try [Sublime Text](http://www.sublimetext.com)
  or [Atom](https://atom.io) (both of which are multiplatform). Configure them
  to be your default git editors by following the instructions on
  [this page](https://help.github.com/articles/associating-text-editors-with-git/).
  Note: programs like Microsoft Word or TextEdit are *not* valid text editors
  here because they don't produce plain text files, but rather more elaborate
  file formats that include text formatting information.
- **A GitHub account**. Create an account by going to
  [github.com](https://github.com).
- **A graphical git client or browser**. This lets you visualise your git
  history more easily, and understand the concepts behind git better. For a
  full list of clients, see [here](http://git-scm.com/downloads/guis). On Mac,
  I recommend [Git Tower](https://www.git-tower.com), though it's not free. The
  cross-platform [SourceTree](https://www.sourcetreeapp.com/) is free and
  available on Windows and Mac. On Linux, try gitg or gitk.


## Create an account on Github

1. Open the [Github link](https://github.com) and sign-up using your email id. 
   If you have student email id, you will get more features, you will be able to 
   create private projects. With personal email id you will be able to create 
   public repostory. i.e., rerepostory will be visible to everyone.

2. Remember your email id and user name; we will be using them while configuring the git intalled in our local machine.

## Git installation

  **Install Git on Windows:**

  1. Download the latest [Git for Windows installer](https://git-for-windows.github.io/).
  2. When you've successfully started the installer, you should see the Git Setup wizard screen. 
  Follow the Next and Finish prompts to complete the installation. 
  3. In your StartUp menu, search for "git bash" and open it. 
  4. Verify installation by typing `git --version` in the git bash window. You will see installed git version like this: git version 2.17.1
  
  **Install Git on Mac OS X:**

  1. Download the latest [Git for Mac installer](https://sourceforge.net/projects/git-osx-installer/files/)
  2. Follow the prompts to install Git.
  3. Open your terminal. 
  3. Verify installation by typing `git --version` in terminal. You will see installed git version like this: git version 2.17.1
  
  **Install Git on Linux:**

  1. Open terminal and run: `sudo apt install git-all` or `sudo yum install git`.
  2. Verify installation by typing `git --version` in terminal. You will see installed git version like this: git version 2.17.1

## Git configuration

You also need to configure git so that it knows your full name and email address. 
Fire up a console/terminal, and type:

{% highlight console %}
$ git config --global user.name "Your Name"
$ git config --global user.email "Your.Name@email.com"
{% endhighlight %}

DO NOT copy the `$` for the command. 
Note that you need to replace "Your name" with your own information. 
Please use the same email address you used for your GitHub account.


## Notes

When typing a passphrase, it might seem that the keyboard isn't working.
However, this is just a security feature (similar to the `*`s you might see
when typing a password on the web). Just go ahead and type the passphrase,
then repeat it as requested.


**For Windows users**: Windows does not have an ssh agent running in the
background by default. If you see the error:

{% highlight console %}
$ ssh-add ~/.ssh/id_rsa
Could not open a connection to your authentication agent.
{% endhighlight %}

you will need to use this command to start the ssh-agent:

{% highlight console %}
$ eval `ssh-agent -s`
{% endhighlight %}

(Be careful to use the proper backtick symbol, usually just above the "Tab"
key on most keyboards; NOT the single quote/apostrophe character.)

Then type:

{% highlight console %}
$ ssh-add ~/.ssh/id_rsa
{% endhighlight %}

(You might need to change the filename from `id_rsa` to the whatever you used.)
See [this StackOverflow answer](http://stackoverflow.com/a/17848593) for more
info.

You need to keep the window on which you launched the ssh-agent open.


## Setup ssh-key

Now our git configuration is completed and we ready to work with git and github. However, each time we make push (upload) 
files on github, we will have to enter git account password. As we will be uploadng document frequently,
it is better set up **ssh-key** to avoide authentication every time we make push. Please follow the instruction
[here](https://help.github.com/en/enterprise/2.17/user/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) 
to create ssh-key and adding it the github account.



The following command also lets you see a rudimentary graphic of your history
without needing a GUI git client:

{% highlight console %}
$ git config --global alias.lsd "log --graph --decorate --pretty=oneline --abbrev-commit --all"
{% endhighlight %}

Then you can get a nice history *within your terminal* by typing:

{% highlight console %}
$ git lsd
{% endhighlight %}

---

Whew! That's quite a lot of stuff! But I hope by the end of the tutorial you'll
find it all useful and worth getting! (Plus: free stuff!)
