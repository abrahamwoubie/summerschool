---
layout: default
title: RNASeq | MLABST'17
---

# MOLECULAR DATA

## Cell type deconvolution task

The aim is to predict the proportion of different cell types from bulk RNASeq using clever approach utilizing data from single cell RNASeq


### Background reading

#### Deconvolution problem

Biologically motivated review: <br>
[https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3874291/](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3874291/)<br>
[http://web.cbio.uct.ac.za/~renaud/CRAN/web/CellMix/_PAGE-Algorithms.html](http://web.cbio.uct.ac.za/~renaud/CRAN/web/CellMix/_PAGE-Algorithms.html)

Technically motivated review: <br>
[https://arxiv.org/pdf/1510.04583.pdf](https://arxiv.org/pdf/1510.04583.pdf)

CIBERSORT method covered in Petri’s lecture: <br>
[http://www.nature.com/nmeth/journal/v12/n5/abs/nmeth.3337.html](http://www.nature.com/nmeth/journal/v12/n5/abs/nmeth.3337.html)

This R package supporting RNA-seq data could be helpful: <br>
[https://bioconductor.org/packages/devel/bioc/vignettes/DeconRNASeq/inst/doc/DeconRNASeq.pdf](https://bioconductor.org/packages/devel/bioc/vignettes/DeconRNASeq/inst/doc/DeconRNASeq.pdf])


#### Single cell RNA-seq

Data: [https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE67835](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE67835) <br>
Code: [https://github.com/seandavi/awesome-single-cell](https://github.com/seandavi/awesome-single-cell)


### Proposed solution

#### Option 1

You may use an existing implementation of cell type deconvolution and focus on innovating how to use scRNAseq in a clever way e.g. to refine the cell type identification [new marker genes]. See above for suggested tools. One plausible approach could be to investigate unsupervised methods to get initial grouping of scRNAseq data into similar cells [possibly representing “ cell types / states” ]. To quantify how well these groupings reflect the original sample grouping [in high dimensional space] consider the metrics presented by Juha.

#### Option 2

You may focus on proposing a new solution to the problem using neural networks.
One solution could be to start with an autoencoder model that learns cell type classification given scRNAseq data.

The simplest such model could be one that gets as input the expression values and as output attempts to reconstruct these values and associate the levels with predicted cell type. This thesis work addressed this problem and could give you insight into the problem: [http://www.diva-portal.org/smash/get/diva2:942241/FULLTEXT01.pdf](http://www.diva-portal.org/smash/get/diva2:942241/FULLTEXT01.pdf)

You would have similar data from human brain as was used there from mouse

However, at this point your model does not yet solve the deconvolution problem. To pass the course, you would in minimum need to discuss how to proceed.

To get a good rank on the leaderboard, you should think a bit further. Given the single cell profiles, you could generate simulated data by pooling a known subset of cells together [e.g. reads from 50 neurons mixed with reads from 50 endothelial cells]. This data and the known mixed proportions could serve as training data for training a deconvolution model. We will post more hints during the 2nd week how to proceed here!

