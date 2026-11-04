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
### The Problem of Multiple Variables - Part I
Oftentimes in science, we're interested not just in if one condition can affect outcomes, but if multiple do. For example, if we're looking at a clinical study, we might be interested in seeing not only how patient outcomes vary by treatment received, but also how outcomes vary by the patient's age, their weight, and so on and so forth.


To begin with, we often want to try and visualize our data to see if any particular groupings happen to stand out. This works well as long as we only have two or three variables we want to visualize, but grows increasingly difficult the more factors that we want to consider. In such cases we can apply a technique for [dimensionality reduction](https://en.wikipedia.org/wiki/Dimensionality_reduction) to our data. These techniques work by effectively compressing the information contained across many variables into a smaller number which we can then visualize.


One such technique which is useful in this regard is [UMAP](https://en.wikipedia.org/wiki/Nonlinear_dimensionality_reduction#Uniform_manifold_approximation_and_projection). This technique calculates the likelihood that points in multivariate space are related, and by iteratively pushing unrelated points apart and pulling related points together, can reconstruct a representation of those relationships using a more manageable number of factors.


1. To get started, open the `dealing_with_multiple_variables.ipynb` file in the `lesson_2` subdirectory of your local repository using Visual Studio Code.
2. Follow the instructions in the notebook until you reach the "Introduction to Multivariate Linear Regression" section, and then return here.

---
