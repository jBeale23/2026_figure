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
In science, we usually think in terms of comparisons and hypotheses about those comparisons. For example, we often say something like, "If we treat these patients with a particular medicine, we expect that their condition will improve." What is being said here is that we want to compare the outcomes for two conditions -- those patients who receive a medicine and those who don't -- and an expectation of what we expect the outcome to be.


Naturally, we want to be able to test this hypothesis, and quantify how likely it is that our hypothesis is wrong. To do so, we can establish what is called a "[null hypothesis](https://en.wikipedia.org/wiki/Statistical_hypothesis_test)". A null hypothesis is effectively the inverse of our stated hypothesis, so in our example, the null hypothesis would be that if we treat patients with this medicine, it will have no effect or make their condition worse.


Once we have our comparison and our hypothesis about it, we then want to determine how likely it is to be correct. We can do so by calculating some kind of "test statistic" about the data, and then determine how likely it is that a test statistic which is at least as large as the one we calculated could have occurred if the null hypothesis is true. The likelihood we calculate for that to occur is a "p-value". If the resulting p-value is below a predefined threshold, then we reject the null hypothesis and say that the result is "significant". This isn't quite the same as saying that our hypothesis is correct, but for an experiment designed with appropriate controls, we can be fairly confident that our hypothesis explains at least some of what's going on.


In cases where we're making multiple hypotheses -- E.G., that any one of multiple medications might improve patient conditions -- we run into an issue. As all a p-value says is that there's some small chance that the null hypothesis is true, if we're working at a p-value of 5% and do 100 tests, we'd expect 5 of those tests to come back as "significant" just due to random chance. We can account for this with a "multiple comparison correction." The two most common of these are the "[Bonferroni Correction](https://en.wikipedia.org/wiki/Bonferroni_correction)" and the "[Benjamini-Hochberg Procedure](https://en.wikipedia.org/wiki/False_discovery_rate#Benjamini%E2%80%93Hochberg_procedure)", with the latter usually being preferred in science.

---
### Parametric, Nonparametric, and the Central Limit Theorem
The [Central Limit Theorem](https://en.wikipedia.org/wiki/Central_limit_theorem) essentially says that if we sample from a distribution and calculate a test statistic, the distribution of that test statistic will eventually resemble a [Normal Distribution](https://en.wikipedia.org/wiki/Normal_distribution#Standard_normal_distribution). These distributions have many useful properties, but the most useful for our purpose is that they show up all over the place in the real world, largely thanks to the Central Limit Theorem.


This useful property means that we can often employ what are called "parametric" statistical tests in research. These tests require that the data they are used on is normally distributed, but offer a great deal of power in exchange, meaning that they are very good at rejecting the null hypothesis when there is a genuine difference present. Some examples of these include the t-test and the ANOVA.


In some cases however, we aren't able to guarantee that a given set of data is normally distributed. In such a case, we use what is called a "nonparametric" statistical test. These tests typically have lower power, but they usually make fewer assumptions about the data, and thus they can be used even for data which isn't normal or has unequal variances between groups. Some examples of these include the Mann-Whitney U test, the Wilcoxon matched-pairs test, and the Kruskal-Wallis test.


To determine which test is applicable, you can generally follow this procedure:
1. Determine if the data is normally distributed or not. This can often be done via the [Shapiro-Wilk Test](https://en.wikipedia.org/wiki/Shapiro%E2%80%93Wilk_test), where we say that the data is likely to be normally distributed if the p-value of the test is greater than our predefined threshold (typically 0.05). Once you know if your data is normal -- and thus able to use parametric tests -- or not, proceed to step 2.
2. Determine how many groups you are comparing. If you're comparing more than two groups, you'll usually want to use the parametric ANOVA test or the nonparametric Kruskal-Wallis test. Meanwhile if you're only comparing two groups, continue to step 3.
3. Determine if the groups are paired or unpaired. Samples being paired means that they depend on each other in some way. E.G. perhaps your measurements are the blood pressures of patients before and after undergoing some kind of treatment. In such a case, the measurements for each individual are paired. If the measurements were instead from two unrelated groups, one of which underwent treatment and one of which did not, the groups would be unpaired. In the case of paired samples, you can use the parametric paired-samples t-test or the nonparametric Wilcoxon matched-pairs test. In the case of unpaired samples, you can typically use the parametric independent samples t-test or the nonparametric Mann-Whitney U test.

---
### An Intro to Polars
[Polars](https://pola.rs/) is a library for Python which is designed to make working with data straightforward, by enabling most of the kinds of functions which can be found in a typical spreadsheet program like Excel to be done programmatically.


1. To get started, open the `introduction_to_statistics.ipynb` file in the `lesson_1` subdirectory of your local repository using Visual Studio Code.
 - This is what's called a Jupyter notebook. It's a file designed to allow you to actively visualize and work with data in an iterative manner, and is commonly used in data science for prototyping and data exploration.
 - These exercises will largely revolve around loading data, visualizing and summarizing it, and selecting particular subsets of it.
2. Follow the instructions in the notebook until you reach the "Introduction to SciPy" section, and then return here.

---
### An Intro to SciPy
[SciPy](https://scipy.org/) is a library for Python which is designed for data analysis. It offers a wide variety of statistical and machine learning functionalities.

1. Return to the Jupyter notebook and follow its instructions until you reach the "Introduction to MatplotLib" section, and then return here.
 - These exercises will focus on running some basic statistical tests to compare some of the groups in the data we looked at in the "Introduction to Polars" section.

---
### An Intro to Matplotlib
[Matplotlib](https://matplotlib.org/) is a library for Python which allows for data visualization and graphing.

1. Return to the Jupyter notebook and follow its instructions until you reach the "Challenges" section, and then return here.
 - These exercises will focus on plotting and visualizing some of the data from the "Introduction to Polars" section.

---
### A Brief Guide on Debugging
During today's challenge, and many times in your life while working with code, you'll likely find things that just don't work. When you do, it's important to understand how to go about fixing them, so here are a few general guidelines on how to troubleshoot and debug most programs.


1. Start with the Error Message. Most of the time when something goes catastrophically wrong, you'll get a helpful error message that tries to convey what exactly happened. Always read these carefully, as they can often tell you what the problem is directly, or at least where to start looking. Sometimes the issue will be as simple as a misspelled function name or typing in the wrong order of parameters, and examining the error message closely will usually reveal problems like that. If it's not enough for you to deduce the issue on its own, it can help you get started with step 2.
2. Consult Previous Work. If you grab a few relevant pieces of information from the Error Message, such as the type of error and the function and program in question, you can often find a solution to the error you're getting by searching with those keywords in Google. Sites such as [StackOverflow](https://stackoverflow.com) will often show up in the search results with people who have had similar issues and advice from others on how to resolve those issues. If those still aren't enough, you can always proceed to step 3.
3. Consult the Documentation. For most pieces of software, especially major ones such as Polars, SciPy, and Matplotlib, the developers provide extensive documentation of nearly every function and how it works. Said documentation will often appear if you use a given function and piece of software's name to search on Google. This documentation usually has extensive explanations of all parameters for a function, often links to further reading on the underlying math in the case of statistical functions from SciPy, and usually links to related functions. Documentation such as this is often the best place to learn the intricate details of how to use something, but it is often more technical in nature than the other options.

---
## Challenges
These are extra activities which shouldn't take you all that long, but will help reinforce some of the things we've practiced today. We'll discuss them during our next lesson, so don't worry if you aren't able to figure something out.
1. Pick two features we haven't already plotted from the Iris dataset, and plot the three flower types using those features. Then calculate the p-value for each of those features being capable of distinguishing between the flower types.
2. Add the figures you've generated to your .gitignore file.
3. Commit the changes you've made to GitHub.
