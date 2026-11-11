# Lesson 3: Introduction to Mass Spectrometry Analysis
---
## Objectives
- Learn the basics of mass spectrometry for proteomics
- Learn the basics of mass spectrometry analysis
---
### Updating the Repository
As with last week, we'll get started today by updating our local repository using the instructions from [lesson 1](../lesson_1/intro_to_stats.md).

---
### The Basics of Mass Spectrometry for Proteomics
In general, [mass spectrometry](https://en.wikipedia.org/wiki/Mass_spectrometry) revolves around the process of taking some sample of interest, ionizing its contents, separating those contents based on their mass to charge ratio, and finally determining the identity and quantity of what was present. In the case of proteomics, typically "bottom-up" experiments revolve around taking a sample of proteins from some source of interest, digesting them with one or more enzymes into their constituent peptides, and then analyzing them via mass spectrometry in order to determine something of biological interest.


Broadly, mass spectrometry allows us to determine changes in protein expression, protein interactions, and alterations in protein modification and structure. In each case, this can provide key mechanistic insight into how exactly a disease progresses or a medicine works in providing treatment. If you would like further reading on the application of mass spectrometry in proteomics, [this paper from Han _et. al._](https://pmc.ncbi.nlm.nih.gov/articles/PMC2642903/) is a great place to start.

---
### How Do You Analyze Mass Spectrometry Data?
In general, mass spectrometry analysis revolves around determining two values for each protein; the p-value of a change in its abundance being just to chance and the fold change of its abundance difference, or a measurement of how large the change actually is. Typically, these values are reported at the level of each protein. For today's work, we'll be starting from the level of individual ions, and working through the full process of doing mass spectrometry analysis using the techniques we discussed in [lesson 1](../lesson_1/intro_to_stats.md).


To this end, we will be working with data from the work of [Koopmans _et. al._](https://pmc.ncbi.nlm.nih.gov/articles/PMC12957516/) in which they use proteomics to study Schizophrenia.


1. Download the required `diann.zip` data file by navigating to your local `lesson_3` directory in Bash and running the following command: `curl ftp://ftp.pride.ebi.ac.uk/pride/data/archive/2026/03/PXD058441/diann.zip -O`. You can then unzip the retrieved `diann.zip` file using `unzip diann.zip`.
 - As an aside, `curl` is a general purpose command for interacting with web links at the terminal. It can be used for downloading and uploading files, along with many other purposes. You can read through its manual page if you're interested in learning more by running `man curl` in your Bash terminal.
2. To get started with the analysis, open the `mass_spectrometry_analysis.ipynb` file in the `lesson_3` subdirectory of your local repository using Visual Studio Code.
3. Follow the instructions provided in the notebook until you reach the end.

---
