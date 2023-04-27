# Genome Assembly using ABySS

To familiarize yourself with the algorithm behind ABySS assembler, here is the [link](https://genome.cshlp.org/content/27/5/768.full.pdf+html) to the ABySS paper.

# Running ABySS on Galaxy

From Tools panel choos [**ABySS** de novo sequence assembler](https://usegalaxy.eu/root?tool_id=toolshed.g2.bx.psu.edu/repos/iuc/abyss/abyss-pe/2.3.4+galaxy1)

and set the following parameters:

- Insert Paired-end library
- two separate datasets: 
- Paired-end reads 1: x.R1.fastq.gz
- Paired-end reads 2: x.R2.fastq.gz
- K-mer length: 41

and `Run Tool`

Inspect the outputs and run quality assessments (e.g., Quast)

