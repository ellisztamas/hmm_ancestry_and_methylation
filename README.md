# hmm_ancestry_and_methylation

Developing a Hidden-Markov model to infer ancestry and DNA methylation status in a cross

## Premise

We want to track how chromatin state, primarily measured as DNA methylation from bisulphite data, is inherited through a cross.
To do this we need to be able to track the ancestry of each section of genome directly from bisulphite short-read data mapped to long-read genome assemblies of the parents.
The plan is to use this to output a file specificying whih reads map to which parent.

We apply this to a cross previously studied by Rahul in his PhD project.

## `chaasm` package

A Python package `chaasm` (Calling Haplotypes and Allele-Specific Methylation) is under development to run the HMM in `02_library/chaasm`.
This needs updating with its own Git repo, and a tutorial on how to use it.

## Data

We use bisulphite data from an F2 cross between accession 6046 and 6191.

### Parental genomes

Soft-links to the long-read assemblies for the two parental genomes are in `01_data/parental_genomes`.
Note that the genome for 6191 differs from the one in `/groups/nordborg/common_data` because Haijun updated it to account for residual heterozygosity based on [Guan et al (2020)](https://academic.oup.com/bioinformatics/article/36/9/2896/5714742).
This link will need updating as other genomes are updated, and 6191 is hopefully merged back in with the others.

We concatenated parental genomes into a single FASTA file including the TAIR10 chloroplast to map reads to.

### 6191x6046 F2 cross

We used the cross studied by Rahul Pisupati in his PhD thesis chosen because they show high and low gene-body methylation.
See [his paper](https://doi.org/10.1371/journal.pgen.1010728) or his thesis for full details.
Briefly, 6046 is from Lóvvik in Northern Sweden, and 6191 from Drakamöllan in Southern Sweden.
Eriko Sasaki did the initial cross, and Rahul Pisupati grew the F2s in both directions in growth chambers at 4°C and 16°C.

His project folder is here:
```
/groups/nordborg/projects/epiclines/005.manu.crosses.2020/
```

Rahul copied raw reads to directory `001.raw_data` in his project folder.
I will try and track down the original files.

## Contributions

Matin Saedi and Rahul Pisupati wrote the code for the HMM
Tom Ellis and Haijun Liu helped with bioinformatic analyses.
Tom and Rahul supervised Matin directly, with Magnus throwing rocks from afar.
