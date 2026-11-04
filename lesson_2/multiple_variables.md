# Lesson 2: Dealing with Multiple Variables
---
## Objectives
- Learn how to visualize multivariate data with UMAP
- Learn the basics of multivariate linear regression
- Learn the importance of cross validation
- Learn the basics of feature selection
---
### Updating a Git Repository
As with last week, the first step for today is to update your local repository. The instructions below are directly copied from [lesson 1](../lesson_1/intro_to_stats.md), and you'll use them at the start of every subsequent lesson.


1. On your computer, navigate to your local copy of the repository, right click, and choose to "Open Git Bash here".
2. Run `git pull --rebase upstream main`.
3. Run `git push --force origin main`.

---
### Some Necessary Software
In addition to `polars`, `scipy`, and `matplotlib` like we worked with last week, we'll need to add a few additional packages to our environment. These packages revolve around machine learning techniques which we can use to handle data with more than a single predictor variable. If you need help with adding them to your Conda environment, take a look at the instructions for updating an environment in [lesson 0](../lesson_0/getting_started.md). Both of these packages are available from Conda itself, so there's no need to worry about adding them to your pip install block.

- `scikit-learn`
- `umap-learn`

---
