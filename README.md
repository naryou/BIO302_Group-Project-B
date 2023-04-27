# Tutorial for BIO302_Group-Project-B

*Students: Jeanine & Jan*

## Study system
*Primula grandis* (Primulaceae)
Endemic to Caucasus; Homostylous (only one flower morph, due to loss of heterostyly)

- Genome size: 900Mb (Flow Cytometry and K-mer count)
- Ploidy: tetraploid, 2n=44
- Data generated: Nanopore (35x total), WGS shotgun, Hi-C (Arima)

![Primula grandis][Pgrandis_NY]

[Pgrandis_NY]: ./Pgrandis.png


## On this [Galaxy history](https://usegalaxy.eu/u/naryou/h/bio302genome-assembly-b), you find the following data

- Whole  Genome Shotgun Sequencing of Primula grandis. This is Illumina short reads, paired-end (PE), 150bp.
- Nanopore reads of P. grandis
& Narcis will add the following:
- Hi-C data. This is also Illumina short reads, paired-end (PE), 150bp, but the read1 and read2 come from stretches of DNA which are in close distance in 3D. 
To refresh your knowledge on Hi-C data, please have a look at LEC2, NGS data generation and handling.
- Reference assembly of P. grandis generated using both long reads (Nanopore) and short reads (Illumina), which will be used for comparison with your *de novo* assembly

## The project will be done in four steps:
- genome profiling using GenomeScope2
- assembly using ABySS (for short reads) and Shasta (for long reads)
- scaffolding using YaHS
- annotation using Repeat Modeler (and Maker if we have time)

You find tutorials for genome profiling, assembly, scaffolding and annotation in this repository. Just navigate to different directories.

