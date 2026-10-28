# Lesson 1: Introduction to Statistics
---
## Objectives
- Learn how to update a Git repository
- Learn what a p-value is and what it means
- Learn the difference between parametric and nonparametric tests
- Learn the basics of manipulating data with Polars
- Learn the basics of using SciPy
- Learn the basics of plotting with Matplotlib
- Learn the basics of troubleshooting code
---
### Updating a Git Repository
Once you've made a fork of a git repository (see [lesson 0](../lesson_0/getting_started.md) if you need a refresher), you'll sometimes want to update it with changes that the original version has made. In today's case, you'll want to do so to get everything you'll need for lesson 1.


1. On your computer, navigate to your local copy of the repository, right click, and choose to "Open Git Bash here".
2. Run `git remote add upstream https://github.com/jBeale23/2026_figure.git` to add the original repository as a place you can pull updates from.
3. Run `git pull --rebase upstream main` this pulls the changes made to the original repository into your local copy, and then applies the changes you've made on top of those. This is done to ensure that the commit history of your repository remains linear, thus making it much easier to go back through if you have to at a later time. If a conflict occurs (meaning both you and the original repository changed the same thing), a window will open to allow you to decide which version of the changes should be kept.
4. Run `git push --force origin main` this pushes the changes you've just applied from the original repository into the version of your repository on GitHub, and rewrites the history of commits to match your local copy. Be very careful with using the `--force` flag, as rewriting history is one of the easiest ways to accidentally overwrite something you didn't mean to.


In the future, we'll start each lesson using the `git pull --rebase upstream main` and `git push --force origin main` commands to update your local repository with new lesson material.

---
### What is a P-Value?
---
### Parametric, Nonparametric, and the Central Limit Theorem
---
### An Intro to Polars
---
### An Intro to SciPy
---
### An Intro to Matplotlib
---
### A Brief Guide on Debugging
---
## Challenges
These are extra activities which shouldn't take you all that long, but will help reinforce some of the things we've practiced today. We'll discuss them during our next lesson, so don't worry if you aren't able to figure something out.
