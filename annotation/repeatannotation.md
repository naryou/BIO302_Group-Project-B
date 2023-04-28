# Annotation of Repeats

## Background
For identification and annotation of transposable element (TE) families, we use the RepeatModeler package. RepeatModeler uses three de novo repeat finding programs ( RECON, RepeatScout and LtrHarvest/Ltr_retriever) which employ complementary computational methods for identifying repeat elements from sequence data.

Here is the link to [RepeatModeler paper](https://www.pnas.org/doi/pdf/10.1073/pnas.1921046117?download=true) and here you find the [GitHub repository](https://github.com/Dfam-consortium/RepeatModeler). 


## Run RepeatModeler on Galaxy  
From Tools panel choose [**RepeatModeler** Model repetitive DNA](https://usegalaxy.eu/root?tool_id=toolshed.g2.bx.psu.edu/repos/csbl/repeatmodeler/repeatmodeler/2.0.3+galaxy0). Make sure that the version is 2.03 (the newest one gives error). 

Choose the fasta file from Shasta and `Run Tool`.


## Run Repeatmasker on Galaxy

From Tools panel choose [RepeatMasker screen DNA sequences for interspersed repeats and low complexity regions](https://usegalaxy.eu/root?tool_id=toolshed.g2.bx.psu.edu/repos/bgruening/repeat_masker/repeatmasker_wrapper/4.1.1) with the follwing parameter setting:

**Genomic DNA**: Scaffolded (using YaHS) fasta genome

**Repeat library source**: choose 'Custom library of repeats' and provide 'output of RepeatModeler (consensus sequences)'

**Output annotation of repeats in GFF format**: Yes

In **Advanced options**:

**Output repetitive regions as lowercase, non-repetitive regions as uppercase**: Yes

**Output list of potentially polymorphic microsatellites**: Yes

and `Run Tool`

The output is a fasta file which is 'masked' for the repeated regions of the genome (they will appear in lower case) and a GFF3 annotation file. This annotated genome is useful for mapping applications and visualization of the repeats in the genome.

