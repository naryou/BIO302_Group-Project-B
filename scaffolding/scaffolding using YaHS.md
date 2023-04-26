# Background
While preparing the Hi-C libray, we digest and ligate DNA sequences which results in ligation of sequence fragments that are in close proximity in 3D space. After Illumina paired-end sequencing, some of the reads are chimeric. The first step is to process the Illumina data and sort out the reads as following:

![canvas](https://user-images.githubusercontent.com/48094864/216301011-d70f8590-da80-4497-9fc0-252705ef15d2.png)


# Pre-processing of Hi-C data using BWA-mem
Despite Hi-C generating paired-end reads, we need to map each read separately. This is because most aligners assume that the distance between paired-end reads fit a known distribution, but in Hi-C data the insert size of the ligation product can vary between one base pair to hundreds of megabases

## step 1: mapping the F and R reads to the contigs 
From Tools panel, choose [**Map with BWA-MEM2**](https://usegalaxy.eu/root?tool_id=toolshed.g2.bx.psu.edu/repos/iuc/bwa_mem2/bwa_mem2/2.2.1+galaxy0)

Set the follwoing parameters:
- “Will you select a reference genome from your history or use a built-in index?”: Use a genome from history and build index
- “Single or Paired-end reads”: Single
- “Select fastq dataset”: Hi-C_dataset_F
- Set read groups information?”: Do not set
- Select analysis mode”: 1.Simple Illumina mode
- “BAM sorting mode”: Sort by read names (i.e., the QNAME field)
  - Rename the output as BAM forward

Now repeat the mapping for *reverse* reads (Hi-C_dataset_R)

## step 2: filter, merge and sort mapped reads

From the Tools panel choose [**Filter and merge** chimeric reads from Arima Genomics](https://usegalaxy.eu/root?tool_id=toolshed.g2.bx.psu.edu/repos/iuc/bellerophon/bellerophon/1.0+galaxy0)

Set the following parameters:
- “First set of reads”: BAM forward
- “Second set of reads”: BAM reverse

Rename the output as BAM Hi-C reads

Now from Tools panel choos [**bedtools BAM to BED** converter](https://usegalaxy.eu/roottool_id=toolshed.g2.bx.psu.edu/repos/iuc/bedtools/bedtools_bamtobed/2.30.0+galaxy2)

Set the following parameters:
- “Convert the following BAM file to BED”: BAM Hi-C reads
- “What type of BED output would you like”: Create a full, 12-column "blocked" BED file
Rename the output as BED unsorted

Finally from Tools panel choose [**sort** data in ascending or descending order](https://usegalaxy.eu/roottool_id=toolshed.g2.bx.psu.edu/repos/bgruening/text_processing/tp_sort_header_tool/1.1.1) with following parameters:

- “Sort Dataset”: BED unsorted
- “on column”: Column: 4
- “with flavor”: Alphabetical sort
- “everything in”: Ascending order

Rename the output as BED sorted.
This is one of the inputs for YaHS.

# Running YaHS on Galaxy

From the Tools panel, choose [**YaHS** yet another HI-C scaffolding tool](https://usegalaxy.eu/root?tool_id=toolshed.g2.bx.psu.edu/repos/iuc/yahs/yahs/1.2a.2+galaxy1)

Now in `Input contig sequences` provide the contig assembly (fasta file, output of the genome assembler) and in `Alignment file of Hi-C reads to contigs` provide the mapped and sorted Hi-C reads (bed file from last step). In `Restriction enzyme sequence(s)` give XXXXX and run the tool.


