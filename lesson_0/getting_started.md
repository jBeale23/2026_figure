# Lesson 0: Getting Started With Scientific Coding
---
## Objectives
- Learn How to Setup a GitHub Account
- Install Visual Studio Code
- Install Conda
- Install Docker
- Install Git
- Learn the Basics of Git
- Learn How to Configure a Conda Environment
---
### Setting Up a GitHub Account
[GitHub](https://github.com) is arguably the most popular remote repository hosting site for Git repositories. It is widely used by most individuals and organizations to collaborate on code, manage versions between multiple developers, and publish releases of software. Some alternatives include [GitLab](https://gitlab.com) and [Gitea](https://about.gitea.com/), but fundamentally they all serve the same purpose of providing a browser-based interface for git repositories.
1. Sign up for an account at this [link](https://github.com/signup) using a personal email.
 - A personal email is recommended, as you'll likely use GitHub far beyond your time at JHU.
---
### Installing Visual Studio Code
Visual Studio Code (VSCode for short) is a multi-language Integrated Development Environment (IDE) common across a large swathe of the software development world. It provides support for most programming languages via its extensions, and integration with useful tools such as linters, formatters, and debuggers. We'll expand on these additional useful tools later.
1. Download the Visual Studio Code installer at this [link](https://code.visualstudio.com/download?_exp_download=d53503e735).
2. Open Visual Studio Code and add the following extensions:
- Python
- Jupyter
---
### Installing Conda
Conda and its alternatives are tools for software version control common in the data science community. Reproducibility is the core principle of software version control. As behavior can change substantially between different versions of software, ensuring that subsequent researchers are using the same versions for an analysis helps guarantee that they can recreate any findings from it. A secondary benefit is reducing the chance of dependency conflicts, where multiple pieces of software depend on different versions of the same package. By isolating different versions of software into separate containers, different stages of analysis can coexist without issue.
1. Install [Anaconda](https://repo.anaconda.com/archive/Anaconda3-2026.07-1-Windows-x86_64.exe), [Miniconda](https://anaconda.com/api/installers/Miniconda3-latest-Windows-x86_64.exe?attr=ZGxzb3VyY2U9d3d3LmFuYWNvbmRhLmNvbSZ0aW1lc3RhbXA9MjAyNi0xMC0xMlQxMiUzQTIwJTNBNDBaJnV0bV9jYW1wYWlnbj1OVUxMJnV0bV9jb250ZW50PU5VTEwmdXRtX21lZGl1bT1hbmFjb25kYSZ1dG1fc291cmNlPWRpcmVjdCZ1dG1fdGVybT1OVUxM&sig=384f7b9589063516884aa01e98ea7f6c4078590a644aa935b8b7afa9dd324821--), or [Mamba](https://github.com/conda-forge/miniforge/releases/download/26.7.2-0/Miniforge3-26.7.2-0-Windows-x86_64.exe).
 - Miniconda or Mamba are preferred over traditional Anaconda as they are smaller installations and tend to produce fewer bugs, and Mamba is substantially faster than the alternatives. Anaconda does provide a Graphical User Interface to ease its use however, and comes with a wide selection of pre-installed software.
2. During installation, make sure to make Conda (or Mamba) available on your PATH.
---
### Installing Docker
Docker is another tool for software version control, though it goes a step beyond Conda. While Conda is largely focused on the data science software ecosystem and only packages a select assortment of related tools, Docker can bundle an entire Linux operating system and any software which runs on it into a container. This is most useful when developing analyses for use on High-Performance Computing Clusters or powerful Linux workstations and servers, and it allows for development and testing in an environment that is identical between anyone who receives the container.
1. Open Powershell or Windows Command Prompt as an Administrator
2. Run `wsl --install` to install Windows Subsystem for Linux
3. Install Docker Desktop at this [link](https://desktop.docker.com/win/main/amd64/Docker%20Desktop%20Installer.exe).
4. In the installer, select Windows Subsystem for Linux as the backend.
---
### Installing Git
Git is the ubiquitous version control system for almost all software development and data analysis. It operates on a core principle of taking snapshots of points in time in a repository's history, called commits, and stacking them on top of one another to assemble a complete history of all changes across a repository's history. Git also provides the ability to branch off different versions of a repository, merge them back together, and much more, though we'll only scratch the surface of its capabilities today.
1. Install Git for Windows at this [link](https://github.com/git-for-windows/git/releases/download/v2.56.0.windows.2/Git-2.56.0.2-64-bit.exe).
2. In the installer, ensure the following configuration options are enabled:
 - Git Bash
 - Git GUI
 - Git LFS
 - Windows Explorer Integration (Git Bash Here + Git GUI Here)
 - Associate .git* configuration files with the default text editor
 - Associate .sh files to be run with Bash
3. Select Visual Studio Code as Git's default editor
4. Override the default branch name for new repositories to `main`
5. Select to use Git from the command line and also from 3rd-Party Software
6. Select to use the bundled OpenSSH
7. Select to use the OpenSSL Library
8. Select to checkout Windows-style, commit Unix-style line endings
9. Select the `Default` git pull behavior

#### Setting up GitHub Authentication
1. Open a Git Bash terminal anywhere.
2. Run `winget install --id GitHub.cli --source winget`.
  - You may need to install winget from the App Installer, if it's not already available on your system.
  - This is installing the Github Credential Manager, allowing your local installation of Git to know what repositories you own on GitHub.
3. Run `gh auth login` and walk through the interactive process to authenticate with GitHub.
---
### Gitting to the Basics with Conda Environments
To get started with Git, you first need a repository. There are two primary ways to create one, depending on what exactly you'd like to do.
1. `git init` This command creates a new, empty repository in your current working directory, perfect as a blank slate for a new project.
2. `git clone <LINK_TO_REPOSITORY>` This command makes a copy of an existing repository with identical history, perfect as a starting point for collaboration, or for building on existing software.

GitHub adds one additional option, called a "Fork" this is effectively a `git clone` that is automatically added to your GitHub account to make it easier to contribute your changes back to the original repository at a later time.

For this project, we'll be working from a "Fork" of this repository as a starting point, and adding on to it with each lesson. You can make one by doing the following steps:
1. Go to the [repository's home page](https://github.com/jbeale23/2026_figure) and at the top right, select the fork button and create a new fork with default settings.
2. On your computer, navigate to where you would like your local copy of the repository, right click, and choose to "Open Git Bash here".
  - This opens a terminal window in the directory you chose, where you can run commands by typing them and hitting "Enter".
  - You can see what's in a directory by running `ls` and change directories by running `cd <DIRECTORY_NAME>`.
3. In the Git Bash terminal, run `git clone https://github.com/YOUR_USERNAME/2026_figure.git`.
  - This makes a local copy of your repository to which you'll make changes.
4. Change into the `2026_figure/lesson_0` directory using `cd`.
5. Run `cat demo_conda_environment.yaml`.
  - `cat` is short for concatenate, and is a simple program that prints the contents of a file to the terminal. If you run it on multiple files, it will print their contents to the terminal in order. This is a very useful feature that can be employed in a lot of data analysis to quickly combine information from a pipeline.
  - This is what's called a Conda environment file. It specifies the versions of software needed to create an environment, and is used to have a reproducible record of that software. Anytime you want to change what's in your environment, you should do so by updating this file.
  - In the environment, you can specify a name (what the environment is called when you activate it), channels (where Conda will get software from), and dependencies (the pieces of software you want installed). These files use the YAML syntax, which you can find information on [here](https://yaml.org/) if you ever need help formatting one.
  - Any package with a `==SOME_NUMBER` syntax is one for which we're specifying a particular version. In this case, we're only pinning the version of python, and letting Conda retrieve the newest version of every other package that is compatible with everything else in the environment.
6. Run `conda env create --file demo_conda_environment.yaml`.
  - This creates a new environment as specified in the environment file, and will likely take a few minutes to run, depending on your internet connection.
7. Now, open the environment file in Visual Studio Code, as we'll be making a couple of changes to it.
  - Under the dependencies, we'll want to add `ipykernel`. This package enables Jupyter notebook support, which we'll use for many of our later exercises.
  - We'll also want to add `numpy>=2.0.0`, `scipy`, `polars`, `pyarrow`, `matplotlib`, and `seaborn`. These extend python's functionalities with a lot of useful mathematical, statistical, and plotting features, all of which are used frequently for data science.
8. Save your changes to the environment file, and return to the Git Bash terminal.
  - You can inspect the environment file with `cat` once again to see that your changes were made successfully.
9. Update your Conda environment with `conda env update --prune --file demo_conda_environment.yaml`.
  - This adds any new packages which you specified in the file to the environment, and removes any old ones which you removed from the file thanks to the `--prune` flag.
10. Next, we'll commit our changes to GitHub.
  - First, run `git add demo_conda_environment.yaml`. This stages the changes you've made to the specified file. You can view those changes with `git diff --cached [FILE_NAME]` to make sure you've only staged what you wanted to, and back out with `git restore --staged <FILE_NAME>` if you realize you've added something you didn't want to.
  - Next, run `git commit`. This adds all of the changes you've staged as a commit to the history of your repository, alongside a description of the changes you've made. Best practice is to summarize the changes you've made briefly, and if you aren't able to do so in a sentence or two, you should likely consider breaking up the changes into smaller commits. You *can* undo a commit, but it's much harder, so be careful before committing.
  - Finally, run `git push`. This pushes all of your committed changes to the remote copy of your repository, in this case hosted on GitHub. You can open your web browser and navigate to `https://github.com/YOUR_USER_NAME/2026_figure` to see your changes.
---
## Challenges
These are extra activities which shouldn't take you all that long, but will help reinforce some of the things we've practiced today. We'll discuss them during our next lesson, so don't worry if you aren't able to figure something out.
1. Add the following additional packages to your Conda environment: `pip` and `flippr`. Flippr is unique in that it must be installed via pip, and thus it has a slightly different syntax than other changes to your environment file. You can find a [Hint](https://www.anaconda.com/docs/getting-started/working-with-conda/packages/pip-install) here if you get stuck.
2. Commit the changes you've made to GitHub.
