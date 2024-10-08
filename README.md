# Phylogenetic Biology - Final Project

## Guidelines - you can delete this section before submission

This is a stub for your final project. Edit/ delete the text in this readme as needed.

There are two ways you can use this document:  
- You can download this file to a folder on your computer, edit this document and add other files (data, code, etc), and then zip up and submit the folder on canvas.
- You can for the [repository](finalproject) containing this document on gitub. Then commit and push your canges to the repository, and submit a link to the repository on canvas.

Github is a great way to work on projects, but also has a steep initial learning curve.


Some guidelines and tips:

- Use the stubs below to write up your final project. Alternatively, if you would like the writeup to be an executable document (with [knitr](http://yihui.name/knitr/), [jupytr](http://jupyter.org/), or other tools), you can create it as a separate file and put a link to it here in the readme.

- For information on formatting text files with markdown, see https://guides.github.com/features/mastering-markdown/ . You can use markdown to include images in this document by linking to files in the repository, eg `![GitHub Logo](/images/logo.png)`.

- The project must be entirely reproducible. In addition to the results, the repository must include all the data (or links to data) and code needed to reproduce the results.

- If you are working with unpublished data that you would prefer not to publicly share at this time, please contact me to discuss options. In most cases, the data can be anonymized in a way that putting them in a public repo does not compromise your other goals.

- Paste references (including urls) into the reference section, and cite them with the general format (Smith at al. 2003).

OK, here we go.

# Title of my project

## Introduction and Goals

The goal of my project is to answer the question: What are the evolutionary relationships among populations of *Aedes albopictus* mosquitoes in their native range of East and Southeast Asia, and how did they spread across the globe? Ultimately this will help answer the longer-term goal of the project I am contributing to, which is to determine the genetic basis of diapause (egg dormancy) in this species.

The methods I will use to do this are running phylogenetic inference programs on the genetic data that my lab has obtained from specimens from many populations. I will compare the resulting phylogenies with population structure diagrams that I am in the progress of creating outside of class. These two approaches will complement each other to give a fuller picture of the history of these populations, including both the populations' diverging evolutionary histories and any history of gene flow between populations. I plan to use IQtree to perform the inference analyses. I also will try to obtain data from *Aedes aegypti* as an outgroup, because others in my lab have worked with *A. aegypti* genetic data, though the nature of my data (SNPs selected specifically as markers from the species *A. albopictus*) may make this difficult to obtain in a form that I can use for cross-species comparison. Last, I will create several trees, one just for Japan (the country with seemingly the most genetic diversity and our most densely sampled region), one for the native range of East and Southeast Asia, and one for all our samples globally, to compare these trees and provide insight into where the introduced populations came from.

The data I will use are SNP chip data from my lab. My lab performed extractions on mosquitoes that were sent to us from entomologists around the globe. The resulting DNA was sequenced on SNP chips such that we obtained ~100,000 SNPs per specimen spaced out roughly evenly across the genome (with about 10 kb gaps between successive SNPs). We have about 10 mosquitoes per population, from ~20 populations across the native range, as well as from ~40 introduced populations globally. 

## Methods

The tools I used were... See analysis files at (links to analysis files).

## Results

The tree in Figure 1...

## Discussion

These results indicate...

The biggest difficulty in implementing these analyses was...

If I did these analyses again, I would...

## References

