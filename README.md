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

The goal of my project is to answer the question: What are the evolutionary relationships among populations of *Aedes albopictus* mosquitoes in their native range of East and Southeast Asia, and do population genetics and phylogenetics give us the same answers to this question? Ultimately this will help answer the longer-term goal of the project I am contributing to, which is to determine the genetic basis of diapause (egg dormancy) in this species.

The methods I will use to do this are running phylogenetic inference programs on the genetic data that my lab has obtained from specimens from many populations. I will compare the resulting phylogenies with population structure diagrams. These two approaches will complement each other to give a fuller picture of the history of these populations, including both the populations' diverging evolutionary histories and any history of gene flow between populations. I plan to use IQtree to perform the inference analyses. To process the population structure data, I will develop an algorithm to create a dendrogram that can be compared to the IQTree phylogeny.

The data I will use are SNP chip data from my lab. My lab performed extractions on mosquitoes that were sent to us from entomologists around the globe. The resulting DNA was sequenced on SNP chips such that we obtained ~100,000 SNPs per specimen spaced out roughly evenly across the genome (with about 10 kb gaps between successive SNPs), then was quality-controlled until only around 20,000 SNPs remained for each mosquito. We have about 10 mosquitoes per population, from 24 populations across the native range.

## Methods

# Data Collection and Quality Control
The genetic data I used were obtained from SNP chips designed for this species. 252 mosquitoes were collected from 24 localities along a transect from northern Japan to Java, Indonesia. Most populations had 12 individuals sampled. The specimens were sent to the Caccone lab, where DNA extraction was performed. Extracted DNA was then sequenced on a SNP chip with 121,946 SNPs per individual. The data were processed for quality control, including missingness, Minor Allele Frequency (MAF), heterozygosity, Hardy-Weinberg equilibrium, relatedness, and linkage disequilibrium (LD). Individuals with over 15% of variants missing were removed from the dataset, and variants that were missing in over 10% of individuals were removed. Individuals with heterozygosity over four standard deviations from the mean were likewise removed. All variants were shown to be in Hardy-Weinberg equilibrium. Last, individuals were screened for relatedness; in pairs of individuals with relatedness of over 0.354, one individual was removed from the pair. Then, four different datasets were made, using two different cutoffs for MAF and two different cutoffs for LD pruning. For MAF, I used 10% and 1% as the cutoffs; for LD, the cutoffs I used were an r2 of 0.1 and 0.01.
 
The quality control steps above yielded four datasets that I used in later analyses, all of which included the same 247 individual mosquitoes but which ranged in number of SNPs per individual from 17,874 (most stringent MAF and LD pruning) to 62,617 (least stringent MAF and LD pruning).
 
 
# Population Structure
	After quality control, the next step was to determine the population structure of our samples. Out of the four possible data sets to input into the population structure analyses, we chose the dataset with an MAF cutoff of 1% and an LD disequilibrium cutoff of r2<0.01 – this represents intermediately stringent quality control, with 21,284 SNPs remaining. The genetic data were first visualized on a PCA plot to see what populations might cluster together (Fig. 3), then were analyzed using the LEA package in R. I also ran a DAPC to further separate clusters.
  
 
I tested clustering using different numbers of ancestral populations (k), from 1 to 25, and obtained the cross-entropy of 5 replicate runs for each value of k. The lowest cross-entropy was found in k=8 (Fig. 4), indicating that there is the best support for 8 population clusters within the native range of *A. albopictus*.
 
 
	To investigate relationships among these population clusters, I created admixture plots for k=1 through k=25, using the lowest-cross-entropy run for each value of k. This assigns each individual a proportion of ancestry derived from one of k inferred ancestral populations. The key insight of my work here was that by examining these admixture proportions, you can create a phylogeny-like structure that can be compared against a traditional IQTree phylogeny.

 The algorithm I created to create a tree-like graph from the population structure data is as follows. For each value of k, there are going to be k clusters, and all 24 of the populations will have one of those clusters compose the plurality of the combined genetic material of all the individuals within that population. So, starting at k=1, assign each population to a single cluster based on which cluster is the plurality of the genetic make-up of that population. At k=1, it is simple; all populations are in the same cluster. Then, increase k by one (k=2). Now, each of the populations will fall into one of two clusters. Increase k again, and the populations can be divided into three groups. Because of this branching pattern, this can be visualized as a tree, where each increase of k by 1 represents a split in the tree (figure 1). This tree can have reticulations in it, because the clusters in k+1 are not necessarily embedded within the clusters in k.
 
 cat("![](", hierarch_clustering_concept.jpg, ")\n\n")
 
 I also created a phylogeny using IQTree2 to compare with the results of the clustering analyses, also based on the MAF>10% and r2<0.01 dataset (Bui Quang et al. 2020). The selected model in IQTree2 was a transversion model with unequal base frequency, using the FreeRate model with 10 categories.	


## Results

The tree in Figure 1 is the tree from IQTree that I will refer to as a reference

## Discussion

These results indicate...

The biggest difficulty in implementing these analyses was...

If I did these analyses again, I would...

## References

