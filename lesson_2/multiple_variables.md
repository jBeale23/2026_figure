# Lesson 2: Dealing with Multiple Variables
---
## Objectives
- Learn how to visualize multivariate data with UMAP
- Learn the basics of multivariate linear regression
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
### The Problem of Multiple Variables - Part II
Beyond just visualizing our data, multiple predictors pose a challenge in that many traditional statistical tests operate on a single variable at a time. While we _could_ approach resolving this by simply running an independent test for each variable and applying a multiple hypothesis correction, that only works in cases where we only care _if_ a given factor is predictive on its own. If instead we want to try and do things like predict outcomes given information about a subject or determine how important a given factor is, we need to take a different approach.


Thus enter, linear regression. Much like you can fit a line to points in two dimensional space by providing a slope and intercept and then optimizing them based on the average distance of the line from each point, we can do the same in higher dimensional space to! In such a case, we simply need to determine a slope for each additional dimension of interest, and we can once again fit a line to use in predicting our outcomes of interest.


Moreover, we can also proceed to determine how much any given variable matters after we've fit our line. In general, a larger slope for a given feature indicates that it does a better job of predicting our outcomes, though we'll go more into feature selection in a later lesson. This comes with a massive caveat however, for this to be true, the magnitude of each feature must be the same. For example, it may make sense to measure the wavelength a protein fluoresces at in nanometers, and the concentration of said protein in milligrams per milliliter. If you're attempting to use both in a predictive model, it probably doesn't make much sense to assume that a slope of 0.2 for the wavelength and 0.2 for the concentration mean the same thing, as the magnitudes of the measurements aren't comparable.


To combat this problem, we can apply scaling to our data so that each variable has the same magnitude. There are many possible ways to do so, ranging from simply dividing by the largest absolute value for each variable to more complex methods which aim to scale and center the data at 0. Fortunately, scikit-learn packages these techniques for us.

1. Return to the Jupyter notebook and follow its instructions until you reach the "Challenges" section, and then return here.

---
## Challenges
These are extra activities which shouldn't take you all that long, but will help reinforce some of the things we've practiced today. We'll discuss them during our next lesson, so don't worry if you aren't able to figure something out.
1. Repeat the UMAP of the iris datasets with UMAP 1 and UMAP 2, but scale our predictor variables before running the UMAP. Did anything change? Why do you think that's the case?
2. Commit the changes you've made to GitHub.
