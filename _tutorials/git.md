---
layout: post
title: Intro to Github for version control
subtitle: Keeping track of your code and its many versions
date: 2017-02-27 08:00:00
author: Gergana
meta: "Tutorials"
tags: github
---

<div class="block">
	<center>
		<img src="{{ site.baseurl }}/img/tutheadergit.png" alt="Img">
	</center>
</div>

### Tutorial Aims:

#### <a href="#version"> 1. Get familiar with version control, git and GitHub</a>

#### <a href="#github2"> 2. Create your own repository and project folder structure</a>

#### <a href="#github3"> 3. Sync and interact with your repository through `RStudio`</a>

#### <a href="#github4"> 4. Sync and interact with your repository through the command line</a>


<a name="version"></a>

## 1. Get familiar with version control, Git and GitHub

## What is version control?

Version control allows you to keep track of your work and helps you to easily explore the changes you have made, be it data, coding scripts, notes, etc. You are probably already doing some type of version control, if you save multiple files, such as `Dissertation_script_25thFeb.R`, `Dissertation_script_26thFeb.R`, etc. This approach will leave you with tens or hundreds of similar files, making it rather cumbersome to directly compare different versions, and is not easy to share among collaborators. With version control software such as <a href = "https://git-scm.com/" target="_blank">Git</a>, version control is much smoother and easier to implement. Using an online platform like <a href = "https://github.com/" target="_blank">Github</a> to store your files means that you have an online back up of your work, which is beneficial for both you and your collaborators.

Git uses the command line to perform more advanced actions and we encourage you to look through the <a href="#command_line"> extra resources we have added at the end of the tutorial later</a>, to get more comfortable with Git. But until then, here we offer a gentle introduction to syncing RStudio and Github, so you can start using version control in minutes.

## What are the benefits of using version control?

Having a GitHub repo makes it easy for you to keep track of collaborative and personal projects - all files necessary for certain analyses can be held together and people can add in their code, graphs, etc. as the projects develop. Each file on GitHub has a history, making it easy to explore the changes that occurred to it at different time points. You can review other people's code, add comments to certain lines or the overall document, and suggest changes. For collaborative projects, GitHub allows you to assign tasks to different users, making it clear who is responsible for which part of the analysis. You can also ask certain users to review your code. For personal projects, version control allows you to keep track of your work and easily navigate among the many versions of the files you create, whilst also maintaining an online backup. 

## How to get started

### Please register on the <a href = "https://github.com/" target="_blank">Github website</a>.

If you are on a personal Windows machine, download and install <a href = "https://git-scm.com/downloads" target="_blank">git</a> for your operating system. Below are some recommended installation instructions, to keep things simple. However, if you know what these options do, and want to change them to suit you, go ahead:

1. For "Select Components", check:
    * "Git Bash Here"
    * "Git GUI Here"
    * "Git LFS (Large File Support)"
    * "Associate .git* ..."
    * "Associate .sh ..."
2. When prompted to choose the default editor, pick Nano (a simple terminal editor) or Notepad++ (a simple graphical editor):
3. For "Adjust your PATH environment", select: "Use Git from Git Bash only"
4. For "Choose HTTPS transport backend", select: "Use the OpenSSL library"
5. For "Configure the line ending conversions", select: "Checkout Windows-style,..."
6. For "Configure the terminal emulator ...", select: "Use MinTTY ..."
7. For "Configure extra options", select: "Enable file system caching"
8. "Enable Git Credential Manager" 

If you are on a personal Mac machine, install Git via Homebrew, which is a package manager for command line programs on Mac. First, open a terminal, which can be found at `~/Application/Utilities/Terminal.app`. Then, copy and paste this line into the terminal and hit "Enter":

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Now enter the following to install Git:

```
brew install git
```

Follow any instructions in the terminal window, you may need to enter your Mac's password or agree to questions by typing `yes`.

The files you put on GitHub will be public (i.e. everyone can see them & suggest changes, but only the people with access to the repository can directly edit and add/remove files). You can also have private repositories on GitHub, which means that only you can see the files. GitHub now offers <a href="https://blog.github.com/2019-01-07-new-year-new-github/" target="_blank">free private repositories as standard</a> with up to three collaborators per repository. They also offer a free education package, with access to software and other perks, you can apply for one using <a href="https://education.github.com/discount_requests/new"> this link.</a>

<a name="github"></a>

## How does version control work?

### What is a repository?

You can think of a repository (_aka_ a repo) as a "master folder", everything associated with a specific project should be kept in a repo for that project. Repos can have folders within them, or just be separate files.

You will have a local copy (on your computer) and an online copy (on GitHub) of all the files in the repository.

### The workflow

The GitHub workflow can be summarised by the "commit-pull-push" mantra.

#### Commit
Once you've saved your files, you need to commit them - this means the changes you have made to files in your repo will be saved as a version of the repo, and your changes are now ready to go up on GitHub (the online copy of the repository).

#### Pull
Now, before you send your changes to Github, you need to pull, i.e. make sure you are completely up to date with the latest version of the online version of the files - other people could have been working on them even if you haven't.

#### Push
Once you are up to date, you can push your changes - at this point in time your local copy and the online copy of the files will be the same.

Each file on GitHub has a history, so instead of having many files like `Dissertation_1st_May.R`, `Dissertation_2nd_May.R`, you can have only one and by exploring its history, you can see what it looked at different points in time.

For example, here is the history for a repo with an R script inside it, as viewed on Github. Obviously it took me a while to calculate those model predictions!

<center> <img src="{{ site.baseurl }}/img/filehistory.png" alt="Img" style="width: 800px;"/> </center>

<a name="github2"></a>

## 2. Create your own repository and project folder structure

To make a repository, go to `Repositories/New repository` - choose a concise and informative name that has no spaces or funky characters in it. This can be your master repo that holds together past and ongoing research, data, scripts, manuscripts. Later on you might want to have more repositories - e.g. a repository associated with a particular project that you want to make public or a project where you are actively seeking feedback from a wider audience. For now, we will focus on organising and using your main repository that holds the files for all your work. With a free GitHub account, you can use public or private respositories. 

<center> <img src="{{ site.baseurl }}/img/newrepo.png" alt="Img" style="width: 800px;"/> </center>

<b>Click on `Initialise repo with a README.md file`. </b>It's common practice for each repository to have a `README.md` file, which contains information about the project, the purpose of the repository, as well as any comments on licensing and data sources. Github understands several text formats, including `.txt` and `.md`. `.md` stands for a file written in <a href="https://en.wikipedia.org/wiki/Markdown">Markdown</a> - you might have used Markdown before from within `RStudio` to create neatly organised reports of your code and its outputs (you can also check out our <a href="https://ourcodingclub.github.io/2016/11/24/rmarkdown-1.html">Markdown tutorial</a>). You can also use Markdown to write plain text files, for example the file you are reading now was written in Markdown.

<center> <img src="{{ site.baseurl }}/img/newrepo2.png" alt="Img" style="width: 800px;"/> </center>

You can directly edit your `README.md` file on Github by clicking on the file and then selecting `Edit this file`.

<center> <img src="{{ site.baseurl }}/img/readme.png" alt="Img" style="width: 800px;"/> </center>


#### Exercise 1: Write an informative README.md file
You can now write the `README.md` file for your repository. To make headings and subheadings, put hashtags before a line of text - the more hashtags, the smaller the heading will appear. You can make lists using `-` and numbers `1, 2, 3, etc.`. __You can discuss the information you want to include among your lab members - here are some things you might want to consider:__

```
- Your name 

- Project title

- Links to website & social media

- Contact details

```


#### Exercise 2: Writing a `.gitignore` file
Repositories often have a file called `.gitignore` and we are about to make one shortly. In this file you specify which files you want Git to ignore when users make changes and add files. Examples include temporary Word, Excel and Powerpoint files, `.Rproj` files, `.Rhist` files, etc. Some files you might want to only have on your local repository (i.e. on your computer), but not online as they might be too big to store online. 

Go to `Create new file` and write a `.gitignore` file within your main repository (not within any folders). You need to call the file `.gitignore` and then add the types of files that Git should ignore on separate lines. You can make this specific to your needs, but as a start, you can copy over this code:

```
# Prevent users to commit their own RProject
.Rproj.user
.Rproj
# Prevent users to commit their own .RData and .Rhistory in mutual area
.RData
.Rhistory
.Rapp.history
# Temporary files
*~
~$*.doc*
~$*.xls*
*.xlk
~$*.ppt*
# Prevent mac users to commit .DS_Store files
*.DS_Store
# Prevent users to commit the README files created by RStudio
*README.html
*README_cache/
#*README_files/
```

#### Exercise 3: Create folders
Discuss among your lab what folders your repository will contain - some examples include: manuscripts, data, figures, scripts, scripts/users/personal_folder_your_name. To make a new folder, click on `Create new file` and add in the name of your new folder, e.g. `manuscripts/` before the file name, in this case a quick `README.md` file. When creating folders within your repo through GitHub's website, you always need to make at least one file associated with them, you can't just create an empty folder. Add a brief explanation of what the folder is for in the `README.md` file, scroll down and click on `Commit new file`. Add a quick message where it says `Create README.md file` in light grey text - we will cover GitHub etiquette later, but for now, when creating/editing files, it's always a good idea to change the default message to a more precise description of what was done and who did it. Stick with the default option of `Commit directly to master branch` - we will explain branches and pull requests at a later stage of the tutorial.

<center> <img src="{{ site.baseurl }}/img/newfolder.png" alt="Img" style="width: 800px;"/> </center>

<a name="etiquette"></a>

### GitHub etiquette

If you'll be sharing the repository with collaborators and even for your own benefit, it's a good idea to define some rules on how to use the repository before we start working within it - for example what GitHub and coding etiquette should people be following? Is there a prefered folder structure, file naming system?

We can make a new `github-etiquette.md` file that outlines the rules that people with access to your repository should follow.

#### Exercise 4: Write a `github-etiquette.md` file
Go to your lab's main repository, click on `Create new file` and add `github-etiquette.md` as a file name. Remember to include the file extension `.md` - otherwise GitHub won't know what's the file format.


<div class="bs-callout-yellow" markdown="1">
#### A few GitHub rules:

- Keep file paths short and sensible.
- Don't use funky characters and spaces in your file names, these cause trouble because of differences in Mac/Windows systems.
- Always __pull__ before you push in case someone has done any work since the last time you pulled - you wouldn't want anyone's work to get lost or to have to resolve many coding conflicts.

</div>

<a name="github3"></a>

## 3. Sync and interact with your repository through `RStudio`

The "commit-pull-push" workflow can be embedded within `RStudio` using "Projects" and enabling version control for them - we will be doing that shortly in the tutorial.

#### Log into your Github account and navigate to the repository you created earlier

Click `Clone or download` and copy the HTTPS link.

<center><img src="{{ site.baseurl }}/img/repo_clone.png" alt="Img" style="width: 1000px;"/></center>

Now open RStudio, click `File/ New Project/ Version control/ Git` and paste the HTTPS link from the Github repository into the `Repository URL:` field. Select a folder on your computer - that is where the "local" copy of your repository will be (the online one being on Github).

<div class="bs-callout-yellow" markdown="1">
#### Hiccups?

We know that there might be problems with the newest updates of the Mac software and installing git and linking it with RStudio. The solutions appear to be very specific to the Mac version you have, so if the above steps didn't work, a good starting point is googling "rstudio can't find git mac **your version**" and trying out the suggested solutions.
</div>

#### Once the files have finished copying across (this may take a while depending on the size of the repo you're joining), you will notice that a few things about your RStudio session have changed: there is a `Git` tab in the top right corner of RStudio, and all the files that are in the repo are now on your computer as well.


<center><img src="{{ site.baseurl }}/img/git_tab.png" alt="Img" style="width: 800px;"/></center>

You are now ready to start making changes and documenting them through Github!  __Note that you can't push empty folders.__

You can open some of the files you made online earlier - for example if you click on your `README.md` file, it will open in `RStudio` and you can make changes. Add some more text just for the sake of exemplifying how version control works. Save the file in the same location (i.e., your repository). 

<center><img src="{{ site.baseurl }}/img/readme_edit.png" alt="Img" style="width: 800px;"/></center>

If you click on the `Git` tab you will see that now your `README.md` file is listed there. Add a tick next to it. Now it has an `M` - this means you have modified the file. If there's an `A`, that's an added file, and a `D` is a deleted file.

If you select the `README.md` file and click on `Diff`, you will see the changes you have made. Once the file is selected, it is `staged`, ready to be commited to Github.

Click on `Commit` and add in your `commit message` - aim to be concise and informative - what did you do? Once you have clicked on `Commit`, you will get a message about what changes you have made.

<center><img src="{{ site.baseurl }}/img/commit_window.png" alt="Img" style="width: 800px;"/></center>

__If you are making your first ever commit, clicking on `Commit` may result in an error message - git will tell you that you need to configure your username and email. This is easily done, and you only need to do it once, afterwards you can commit-pull-push at your convenience!__

In the top right corner of the RStudio screen, click on `More/Shell`. __NOTE: If using a Windows PC, DO NOT use the Shell through RStudio. Instead, find the Git Bash application on your computer and use the command line from it.__

<center> <img src="{{ site.baseurl }}/img/shell.png" alt="Img" style="width: 700px;"/> </center>

### Copy the following code:

```
git config --global user.email your_email@example.com
# Add the email with which you registered on GitHub and click Enter

git config --global user.name "Your GitHub Username"
# Add your username and click Enter
```

### If it worked fine, there will be no messages, you can close the shell window and do your commit again, this time it will work!

You will see a message saying that your branch is now one commit ahead of the `origin/master` branch - that is the branch that is on Github - we now need to let Github know about the changes we have made.

<center><img src="{{ site.baseurl }}/img/git4.png" alt="Img" style="width: 700px;"/></center>

We can't repeat it enough: __always `Pull` before you `Push`.__ `Pull` means that you are retrieving the most recent version of the Github repository onto your local branch - this command is especially useful if several people are working within the same repository - imagine there was a second script examining soil pH along this elevation gradient, and your collaborator was working on it the same time as you - you wouldn't want to "overwrite" their work and cause trouble. In this case, you are the only one working on these files, but it's still good to develop the practice of pulling before you push. Once you've pulled, you'll see a message that you are already up to date, you can now push! Click on `Push`, wait for the loading to be over and then click on `Close` - that was it, you have successfully pushed your work to Github!

Go back to your repository on Github, where you can now see all of your updated files online.

<center><img src="{{ site.baseurl }}/img/updated_repo.png" alt="Img" style="width: 800px;"/></center>

Click on your script file and then on `History` - this is where you can see the different versions of your script - obviously in real life situations you will make many changes as your work progresses - here we just have two. Thanks to Github and version control, you don't need to save hundreds of almost identical files (e.g. `Dissertation_script_25thFeb.R`, `Dissertation_script_26thFeb.R`) - you have one file and by clicking on the different commits, you can see what it looked like at different points in time.

<center><img src="{{ site.baseurl }}/img/repo_history.png" alt="Img" style="width: 800px;"/></center>

__You are now ready to add your scripts, plots, data files, etc. to your new project directory and follow the same workflow as outlined above - stage your files, commit, pull, push.__

### Potential problems

Sometimes you will see error messages as you try to commit-pull-push. Usually the error message identifies the problem and which file it's associated with, if the message is more obscure, googling it is a good step towards solving the problem. Here are some potential problems that might arise:

#### Code conflicts

While you were working on a certain part of a script, someone else was working on it, too. When you go through commit-pull-push, GitHub will make you decide which version you want to keep. This is called a code conflict, and you can't proceed until you've resolved it. You will see arrows looking like `>>>>>>>>>` around the two versions of the code - delete the version of the code you don't want to keep, as well as the arrows, and your conflict should disappear.

#### Pushing the wrong files
If you accidentally push what you didn't intend to, deleted many things (or everything!) and then pushed empty folders, you can revert your commit. You can keep reverting until you reach the point in time when everything was okay. This is an easy way out if you're the only person working in the repository - __be aware that if there are other people that have committed to the repository, reverting will also undo all of their work, as reverting refers to the repository as a whole, not just your own work in it.__

Using these "undo" commands can be daunting, so make sure you read up on the different commands before you attempt anything that may delete work permanently: <a href="https://www.atlassian.com/git/tutorials/undoing-changes/git-revert" target="blank"> here's </a> a starter. It's a good idea to regularly back up your repository to an external hard drive _juuuust_ in case!  

<hr>
<hr>

<a name="command_line"></a>

<a name="github4"></a>

## 4. Sync and interact with your repository through the command line


Traditionally, Git uses the command line to perform actions on local Git repositories. In this tutorial we ignored the command line but it is necessary if you want more control over Git. There are several excellent introductory guides on version control using Git, e.g. <a href = "http://simon-m-mudd.github.io/NMDM_book/#_version_control_with_git" target="_blank">Prof Simon Mudd's Numeracy, Modelling and Data management guide</a>, <a href = "https://swcarpentry.github.io/git-novice/" target="_blank">The Software Carpentry guide</a>, and this <a href = "https://github.com/BES2016Workshop/version-control" target="_blank">guide from the British Ecological Society Version Control workshop </a>. For more generic command line tools, look at this <a href="https://www.git-tower.com/blog/command-line-cheat-sheet">general cheat-sheet</a> and this <a href="https://github.com/0nn0/terminal-mac-cheatsheet">cheat-sheet for mac users</a>. We have also created a table and flow diagram with some basic Git commands and how they fit into the Git/Github workflow. Orange lines refer to the core workflow, the blue lines describe extra functions and the green lines deal with branches:

<center><img src="{{ site.baseurl }}/img/git_cli_nmdm.png" alt="Img" style="width: 850px;"/></center>

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;}
.tg .tg-yw4l{vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-yw4l"><b>Command</b></th>
    <th class="tg-yw4l"><b>Origin</b></th>
    <th class="tg-yw4l"><b>Destination</b></th>
    <th class="tg-yw4l"><b>Description</b></th>
  </tr>
  <tr>
    <td class="tg-yw4l"><code>git clone REPO_URL</code></td>
    <td class="tg-yw4l">Personal Github</td>
    <td class="tg-yw4l">Local</td>
    <td class="tg-yw4l">Creates a local copy of a Github repo. The URL can be copied from Github.com by clicking the `Clone or Download` button.</td>
  </tr>
  <tr>
    <td class="tg-yw4l"><code>git add README.md</code></td>
    <td class="tg-yw4l">Working Dir</td>
    <td class="tg-yw4l">Staging Area</td>
    <td class="tg-yw4l">Add "README.md" to staging area.</td>
  </tr>
  <tr>
    <td class="tg-yw4l"><code>git commit</code></td>
    <td class="tg-yw4l">Staging Area</td>
    <td class="tg-yw4l">Local</td>
    <td class="tg-yw4l">Commits changes to files to the local repo.</td>
  </tr>
  <tr>
    <td class="tg-yw4l"><code>git commit -a</code></td>
    <td class="tg-yw4l">Working Dir</td>
    <td class="tg-yw4l">Local</td>
    <td class="tg-yw4l">adds and commits all file changes to the local repo.</td>
  </tr>
  <tr>
    <td class="tg-yw4l"><code>git pull</code></td>
    <td class="tg-yw4l">Personal Github</td>
    <td class="tg-yw4l">Local</td>
    <td class="tg-yw4l">Retrieve any changes from a Github repo.</td>
  </tr>
  <tr>
    <td class="tg-yw4l"><code>git push</code></td>
    <td class="tg-yw4l">Local</td>
    <td class="tg-yw4l">Personal Github</td>
    <td class="tg-yw4l">Sends commited file changes to Github repo.</td>
  </tr>
  <tr>
    <td class="tg-yw4l"><code>git merge</code></td>
    <td class="tg-yw4l">Other branch</td>
    <td class="tg-yw4l">Current branch</td>
    <td class="tg-yw4l">Merge any changes in the named branch with the current branch.</td>
  </tr>
  <tr>
    <td class="tg-yw4l"><code>git checkout -b patch1</code></td>
    <td class="tg-yw4l">NA</td>
    <td class="tg-yw4l">NA</td>
    <td class="tg-yw4l">Create a branch called "patch1" from the current branch and switch to it.</td>
  </tr>
  <tr>
    <td class="tg-yw4l"><code>git init</code></td>
    <td class="tg-yw4l">NA</td>
    <td class="tg-yw4l">NA</td>
    <td class="tg-yw4l">Initialise a directory as a Git repo.</td>
  </tr>
  <tr>
    <td class="tg-yw4l"><code>git log</code></td>
    <td class="tg-yw4l">NA</td>
    <td class="tg-yw4l">NA</td>
    <td class="tg-yw4l">Display the commit history for the current repo</td>
  </tr>
  <tr>
    <td class="tg-yw4l"><code>git status</code></td>
    <td class="tg-yw4l">NA</td>
    <td class="tg-yw4l">NA</td>
    <td class="tg-yw4l">See which files are staged/unstaged/changed</td>
  </tr>
  <tr>
    <td class="tg-yw4l"><code>git diff</code></td>
    <td class="tg-yw4l">NA</td>
    <td class="tg-yw4l">NA</td>
    <td class="tg-yw4l">See the difference between staged uncomitted changes and the most recent commit</td>
  </tr>
  <tr>
    <td class="tg-yw4l"><code>git stash</code></td>
    <td class="tg-yw4l">NA</td>
    <td class="tg-yw4l">NA</td>
    <td class="tg-yw4l">Save uncommitted changes in a temporary version and revert to the most recent commit</td>
  </tr>
</table>

Below is a quick exercise so you can familiarise yourself with these command line tools. There are a few ways to use interact with Git using the terminal:

1. If you are already in RStudio on a Mac or Linux machine, you can open a terminal within RStudio by going to `Tools -> Terminal -> New Terminal` in the menu. 

<center><img src="{{ site.baseurl }}/img/rstudio_new_terminal.png" alt="Img" style="width: 700px;"/></center>

2. If you are on a Mac or Linux machine you could just open a terminal program and run Git from there. Most Mac and Linux machines will have Git installed by default. On Mac you can go open a terminal by going to: `Applications/Utilities/Terminal.app`.
3. If you are on a personal Windows machine, you can run Git using Git Bash, which can be installed when you installed Git.

Once you have opened a terminal using one of the above methods, start by creating a folder somewhere on your local system called `git_test`, using the `mkdir` (make directory) command by typing the following into the terminal and hitting "Enter":

```shell
mkdir git_test
```

Then enter that folder using `cd` (change directory):

```shell
cd git_test
```

Then, make the folder into a Git repository:

```shell
git init
```

Now the folder has been made into a Git repository, allowing you to track changes to files. Now, lets create a `README.md` file inside the repository and put some text in it, using whatever text editor you are comfortable with. Make sure to place this `README.md` file into the repository folder on your device so it can be found! 

<div class="bs-callout-blue" markdown="1">
#### Creating a README from scratch

Your computer probably comes with a text editor, such as Notepad for Windows or TextEdit for Mac. Open a new doc, type your information, and save it as `README.md` (with TextEdit, you might have to save it as .rf first, then change the extension in your Finder.) 

If you want to do it from the comfort of RStudio, you can create a new RMarkdown file, and save it while changing the extension from `.Rmd` to `.md`. 

</div>

Now, to add the file to be tracked by the Git repository:

```shell
git add README.md
```

The file has now been added to the staging area, but has not yet been committed to a version of the repository. To commit a version:

```shell
git commit
```

You then have to enter a commit message using the text editor which appears, If you have selected Vim as the default text editor, you will need to press `i` before you can type, then `Esc` when you are finished typing. To save and exit, type `:wq`.

Currently, the Git repository is still only on our local computer. Versions are being committed, but they are not being backed up to a remote version of the repository on Github. Go to Github and create a repository called `git_test`, like you did earlier on in the workshop, but this time don't create a `README.md` because we have just made one on the local computer. Now, copy the HTTPS link for that repository. In the terminal, link the local Git repository with the remote repository using the following code, replacing `<HTTPS_LINK>` with the link you copied:

```shell
git remote add origin <HTTPS_LINK>
```

Then make the first push to that newly linked remote repository:

```shell
git push -u origin master
```

Now you can continue editing files, adding changes (`git add <FILE>`), committing changes (`git commit`), pulling (`git pull`) and pushing (`git push`) changes, similar to the process you did with clicking buttons in RStudio. Feel free to explore some of the more advanced commands laid out in the table and flow diagram above. You can also check out a more advanced command line tutorial written by <a href = "http://simon-m-mudd.github.io/NMDM_book/#_version_control_with_git" target="_blank">Prof Simon Mudd for Numeracy, Modelling and Data management guide</a>.


### This tutorial was developed as part of the collaboration between Coding Club and the NERC E3 Doctoral Training Programme. To learn more about the E3 DTP, check out  <a href="http://e3dtp.geos.ed.ac.uk/" target="_blank">the programme's website.</a>

<a href="http://e3dtp.geos.ed.ac.uk/"><img src="{{ site.baseurl }}/img/dtp_for_cc.jpg" alt="Img" style="width: 600px;"></a>
	
<hr>
<hr>

__Check out <a href="https://ourcodingclub.github.io/workshop/" target="_blank">this page</a> to learn how you can get involved! We are very happy to have people use our tutorials and adapt them to their needs. We are also very keen to expand the content on the website, so feel free to get in touch if you'd like to write a tutorial!__


This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/). <a href="https://creativecommons.org/licenses/by-sa/4.0/"><img src="https://licensebuttons.net/l/by-sa/4.0/80x15.png" alt="Img" style="width: 100px;"/></a>

<h3><a href="https://www.surveymonkey.co.uk/r/NXNHYYX" target="_blank">&nbsp; We would love to hear your feedback, please fill out our survey!</a></h3>
<br>
<h3>&nbsp; You can contact us with any questions on <a href="mailto:ourcodingclub@gmail.com?Subject=Tutorial%20question" target = "_top">ourcodingclub@gmail.com</a></h3>
<br>
<h3>&nbsp; Related tutorials:</h3>

{% assign posts_thresh = 8 %}

<ul>
  {% assign related_post_count = 0 %}
  {% for post in site.posts %}
    {% if related_post_count == posts_thresh %}
      {% break %}
    {% endif %}
    {% for tag in post.tags %}
      {% if page.tags contains tag %}
        <li>
            <a href="{{ site.url }}{{ post.url }}">
	    &nbsp; - {{ post.title }}
            </a>
        </li>
        {% assign related_post_count = related_post_count | plus: 1 %}
        {% break %}
      {% endif %}
    {% endfor %}
  {% endfor %}
</ul>
<br>
<h3>&nbsp; Subscribe to our mailing list:</h3>
<div class="container">
	<div class="block">
        <!-- subscribe form start -->
		<div class="form-group">
			<form action="https://getsimpleform.com/messages?form_api_token=de1ba2f2f947822946fb6e835437ec78" method="post">
			<div class="form-group">
				<input type='text' class="form-control" name='Email' placeholder="Email" required/>
			</div>
			<div>
                        	<button class="btn btn-default" type='submit'>Subscribe</button>
                    	</div>
                	</form>
		</div>
	</div>
</div>

<ul class="social-icons">
	<li>
		<h3>
			<a href="https://twitter.com/our_codingclub" target="_blank">&nbsp;Follow our coding adventures on Twitter! <i class="fa fa-twitter"></i></a>
		</h3>
	</li>
</ul>
