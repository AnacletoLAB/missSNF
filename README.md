# miss-SNF: a multimodal patient similarity network integration approach to handle completely missing data sources

Precision medicine leverages patient-specific multimodal data to improve prevention, diagnosis, prognosis and treatment of diseases. Advancing precision medicine requires the non-trivial integration of complex, heterogeneous and potentially high-dimensional data sources, such as multi-omics and clinical data. 
In literature several  approaches have been proposed to manage missing data, but usually limited to the recovery of subsets of features for a subset of patients. A largely overlooked problem is the integration of multiple sources of data when one or more of them are completely missing for a subset of patients, a relatively common condition  in clinical practice.

We propose miss-Similarity Network Fusion (miss-SNF), a novel general-purpose data integration approach designed to manage completely missing data in the context of patient similarity networks.
Miss-SNF integrates incomplete unimodal patient similarity networks by leveraging a non-linear message-passing strategy borrowed from the SNF algorithm.  
Miss-SNF is able to recover missing patient similarities and is ``task agnostic'', in the sense that can integrate partial data for both unsupervised and supervised prediction tasks.
Experimental analyses on nine cancer datasets from The Cancer Genome Atlas (TCGA) demonstrate that miss-SNF achieves state-of-the-art results in recovering similarities and in identifying patients subgroups enriched in clinically relevant variables and having differential survival. Moreover, amputation experiments show that miss-SNF supervised prediction of the overall survival and progression-free interval events with completely missing data achieves results comparable to those obtained when all the data are available.

<div align="center">
<img src="./man/figures/miss-SNF_logo.svg" alt="miss-SNF logo" width="275"/>
</div>

## Installation

The "miss-SNF" package can be installed using devtools. Please
follow these steps:

0. Download from [github](https://github.com/AnacletoLAB/missSNF) or zenodo (doi:10.5281/zenodo.14945615) this repository. Alternatively, you can clone the repository from github using the following command:

```
# Code to clone repository
git clone https://github.com/AnacletoLAB/missSNF.git
```

You can download the compressed _.zip_ file containing this repository using the "< > Code" button in github (always decompress the folder before installation).

1. Install devtools using:

```
install.packages("devtools");
```

2. Load devtools package:

```
library("devtools");
```

3. Then, you can install miss-SNF:

```
# Install miss-SNF
install("./missSNF");
```

4. Now miss-SNF can be used as every R package:

```
# Load package
library(missSNF);

# View documentation
?miss.snf()
```

## Additional options

miss-SNF implementation can impute missing values using simple strategies (i.e. mean or median imputation). Moreover, you can leverage the p-step Random Walk Kernel[^2][^3] to compute the "global" similarity matrix $P$ and/or 1-step Random Walk Kernel to compute the "local" similarity matrix $S$ of the algorithm. 

These options were not tested in the experiments presented in the submitted paper [^1].

## References
[^1]: Jessica Gliozzo, Mauricio A. Soto Gomez, Arturo Bonometti, Alex Patak, Elena Casiraghi and Giorgio Valentini. "miss-SNF: a multimodal patient similarity network integration approach to handle completely missing data sources." Bioinformatics **[Submitted]**

[^2]: Smola, Alexander J., and Risi Kondor. "Kernels and regularization on graphs." Learning Theory and Kernel Machines: 16th Annual Conference on Learning Theory and 7th Kernel Workshop, COLT/Kernel 2003, Washington, DC, USA, August 24-27, 2003. Proceedings. Berlin, Heidelberg: Springer Berlin Heidelberg, 2003.

[^3]: Re, Matteo, Marco Mesiti, and Giorgio Valentini. "A fast ranking algorithm for predicting gene functions in biomolecular networks." IEEE/ACM Transactions on Computational Biology and Bioinformatics 9.6 (2012): 1812-1818.

