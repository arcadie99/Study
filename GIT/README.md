# GIT 


Git is officially defined as a *distributed version control system* (VCS).


In other words, it's a system that tracks changes to our project files over time. It enables us to record project changes and go back to a specific version of the tracked files, at any given point in time.  This system can be used by many people to efficiently work together and **collaborate on team projects**, where each developer can have their own version of the project, distributed on their computer. Later on, these individual versions of the project can be merged and adapted into the main version of the project.


Basically, it's a massively popular tool for coordinating parallel work and managing projects among individuals and teams. Needless to say, knowing how to use Git is one of the most important skills for any developer nowadays - and it's definitely a great addition to your resume!


---

## Instalation and version

On unix system git comes with preinstalled with the OS. If it's not installed, just check the [Official Documentation](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

To check the installed version on the system, simple run the command in the CLI.

> git --version

If git is installed, it will return the GIT version number wich is installed.


---


## Initial configuration

When first time use git on the machine or the project each user must to make some basic configurations like set the username and email. This can be done with the next commands.

> :warning: One important point is that you work on server or other machine that are used by more developers, you must run the next commands from inside of your home directory. This will generate an .gitconfig file with your user and email. Otherwise it will configure in the project and other developers will make the commits from your name. More detail in [Official Documentation](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)


> git config user.name "username"

> git config user.email "user@email.com"


Also to view which configuration values are used and from which config, just need to run te command.

>  git config --list --show-origin


---

# GIT initialization of the project

To start tracking the project with VCS just go inside the project folder and simple type the command.

> git init

This command will create and folder .git and inside we will find the few other folder and some files with configs. Basic configurations are stored in the file .git/config

At this point nothin in project are tracked by the VCS. To start tracking all the files need to run the command.

> git add .

Create an snapshot of the curent files and commit them. 

> git commit -m 'Initial commit'




