# GIT


Git is officially defined as a *distributed version control system* (VCS).


In other words, it's a system that tracks changes to our project files over time. It enables us to record project changes and go back to a specific version of the tracked files, at any given point in time.  This system can be used by many people to efficiently work together and **collaborate on team projects**, where each developer can have their own version of the project, distributed on their computer. Later on, these individual versions of the project can be merged and adapted into the main version of the project.


Basically, it's a massively popular tool for coordinating parallel work and managing projects among individuals and teams. Needless to say, knowing how to use Git is one of the most important skills for any developer nowadays - and it's definitely a great addition to your resume!


---

## Instalation and version

On unix system git comes with preinstalled with the OS. If it's not installed, just check the [Official Documentation](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

To check the installed version on the system, simple run the command in the CLI.

```bash
  git --version
```

If git is installed, it will return the GIT version number which is installed.


---


## Initial configuration

When first time use git on the machine or the project each user must to make some basic configurations like set the user name and email. This can be done with the next commands.

> :warning: One important point is that you work on server or other machine that are used by more developers, you must run the next commands from inside of your home directory. This will generate an .gitconfig file with your user and email. Otherwise it will configure in the project and other developers will make the commits from your name. More detail in [Official Documentation](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)


```bash
  git config user.name "username"

  git config user.email "user@email.com"
```

Also to view which configuration values are used and from which config, just need to run the command.

```bash
  git config --list --show-origin
```

---

## GIT initialization of the project and some basic file manipulations

To start tracking the project with VCS just go inside the project folder and simple type the command.

```bash
  git init
```

This command will create and folder .git and inside we will find the few other folder and some files with configs. Basic configurations are stored in the file .git/config

At this point nothing in project are tracked by the VCS. To start tracking all the files need to run the command.

```bash
  git add .
```

In case you want to start tracking one file simple just indicate the file name instead of .(dot)

Create an snapshot of the current files and commit them.  

```bash
  git commit -m 'Initial commit'
```


After initiailizate of the project sometime we need to ignore some log files, or some libs or whatever. To make this easy we need inside our project folder to create an file named '.gitignore' and inside just to write files, or extension we want to ignore. Inside of '.gitignore' file we can write with some basic shell regular expressions.


When we want to remove the file from the project, move it to the unstaged area we can use the next command.

```bash
  git rm file
```

When you added some files from mistake and don't want to staging it just simple use the command.

```bash
  git rm --cached file
```

this will move file to the untracked zone and dissapear from commit.

To rename the file and to let the git to understand that action we can use the next command.

```bash
  git mv file newfilename
```

---


## GIT log

This is a utility for view the commits during the timeline of the project. standart commands just show some basic informations about who made the commit, when, and hash of the commit. Timeline of commits are inversed.

```bash
  git log
```

When we want to view the changes which was made in commits we can use -p or --patch, this will display the patch diferences

```bash
  git log -p
```

To view a summary of each commit can use another parameter --stat. This parameter will show information like on push or pull.

```bash
  git log --stat
```

---

## Undoing Things

In case you made a commit but forget to add a file or don't change some configurations you can repair the commit with the --amend parameter. This help to exclude the case when you have a commit like 'oops, forget to change the file'

```bash
  git commit -m 'Initial commit'

  git add forgotten_file

  git commit --amend
```

In case you don't have changed something in files or add something you simple can just change the commit message.

If from mistake you stage all files but you need to make a separate commit with other, to unstage the file just use the command bellow.

```bash
   git reset HEAD file
```

after that command the file will be unstaged from commit, and we can add it in another commit without losing the information.

For casess when we need to delete all changes in file until the last commit we just can use the command

```bash
   git checkout file
```


Another point is to use restore parameter to unstaging and to undo the changes in the file.

```bash
# unstaging the file from staged
   git restore --staged file
# undo all the changes in the file until the last commit
   git restore file
```

---
