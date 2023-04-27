## Background

An important step before genome assembly is genome profiling, where frequency of k-mers within raw sequencing reads are analyzed to estimate genome characteristics such as size, heterozygosity, and repetitiveness.

Here is the [link](https://www.nature.com/articles/s41467-020-14998-3) to GenomeScope2 paper. 

## Running Meryl and GenomeScope2 on Galaxy

We will first use Meryl to create a K-mer database, then generate a histogram. This histogram is then used in GenomeScope2 for profiling analysis. Follow the 'Genome profile analysis' section in the VGP assembly pipeline [here](https://training.galaxyproject.org/training-material/topics/assembly/tutorials/vgp_genome_assembly/tutorial.html#genome-profile-analysis) 

As input sequences for Meryl, use the nanopore data (instead of HiFi_collection) 



