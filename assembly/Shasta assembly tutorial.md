# Genome assembly using Shasta

## Background

Shasta is a de novo assembler for long reads, optimized for Oxford Nanopore (ONT) reads. You can find the paper describing Shasta [here](https://www.nature.com/articles/s41587-020-0503-6) and the GitHub repository [here](https://github.com/paoloshasta/shasta).

## Running Shasta on Galaxy

From Tools panel choose [**Shasta** De novo assembly of long read sequencing data](https://usegalaxy.eu/root?tool_id=toolshed.g2.bx.psu.edu/repos/iuc/shasta/shasta/0.6.0+galaxy0)

- As Input read file(s) provide the nanopore data
- Click on Yes for all three types of output options
- MinReadLength: 5000

and Run Tool.

Inspect the outputs. Run quality assessment (e.g. Quast) and visualize the genome graph is Bandage.

