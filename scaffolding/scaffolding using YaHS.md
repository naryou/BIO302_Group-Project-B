# Background
While preparing the Hi-C libray, we digest and ligate DNA sequences which results in ligation of sequence fragments that are in close proximity in 3D space. After Illumina paired-end sequencing, some of the reads are chimeric. The first step is to process the Illumina data and sort out the reads as following:

![canvas](https://user-images.githubusercontent.com/48094864/216301011-d70f8590-da80-4497-9fc0-252705ef15d2.png)


# Pre-processing of Hi-C data using BWA-mem
Despite Hi-C generating paired-end reads, we need to map each read separately. This is because most aligners assume that the distance between paired-end reads fit a known distribution, but in Hi-C data the insert size of the ligation product can vary between one base pair to hundreds of megabases

From Tools panel, choose [Map with BWA-MEM2](https://usegalaxy.eu/root?tool_id=toolshed.g2.bx.psu.edu/repos/iuc/bwa_mem2/bwa_mem2/2.2.1+galaxy0)
Set the follwoing parameters:




# Running YaHS on Galaxy

From the Tools panel, choose [**YaHS** yet another HI-C scaffolding tool](https://usegalaxy.eu/root?tool_id=toolshed.g2.bx.psu.edu/repos/iuc/yahs/yahs/1.2a.2+galaxy1)

Now in `Input contig sequences` provide the contig assembly (fasta file, output of the genome assembler) and in `Alignment file of Hi-C reads to contigs` provide the mapped and sorted Hi-C reads (bed file from last step). In `Restriction enzyme sequence(s)` give XXXXX and run the tool.


