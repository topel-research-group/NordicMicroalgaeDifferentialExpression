# Differential gene expression experiment involving _Skeletonema marinoi_ and _Nannochloropsis granulata_

* Fix the nanopore-derived R05 transcriptome
  * We have the transcripts in FASTA format

* Locate a reliable Nannochloropsis transcriptome
  * No N. granulata transcriptomes on NCBI, only genomes
  * A couple of N. gaditana transcriptomes, including:
    * https://www.ncbi.nlm.nih.gov/nuccore/480473993
    * https://www.ncbi.nlm.nih.gov/bioproject/157493
  * Will likely have to assemble our own N. granulata transcriptome

For the R commands:
* What is the hypothesis we're testing?
* What is the control?

#####

Summer - 18C, summer light intensity
* Skel - Taken at 4 days (expo), reached stat at 7d
* Nanno - 7 (or 10) days (expo), 18d stat
* More lipids going from expo to stat

Winter - 
* Slow Nanno growth, Smar okay
  * Nanno doesn't reach stat? Experiment stopped at ~23 days
* Lipid data already taken; how does it compare to RNAseq data?

Comparisons - for both Smar and Nanno:
* Summer - Exponential vs. Stationary
* Winter - Exponential vs. Stationary
* Exponential - Summer vs. Winter
* Stationary - Summer vs. Winter

Check for up-/down-regulated pathways specifically, not just individual genes
* Pathway Tools?
* GO enrichment?


#####

## Workflow:

1. QC the data

2. Run Trinity on each of the datasets to generate transcriptome assemblies
* CHECK READ DIRECTIONALITY
* CHECK NUMBER OF READ PAIRS; MAY NEED NORMALISATION

3. Run Transrate on the assemblies to ensure good quality transcripts
* Run Salmon on all good.*.fa files, but check all outputs

* NEED TO CLUSTER THE RESULTS OF TRINITY/TRANSRATE INTO A FULL TRANSCRIPTOME;
  REMOVE READS WITH WHAT PERCENTAGE IDENTITY?

4. Run Salmon on the transcripts to quantify them and generate abundance data

5. Run DESeq2 on the samples to perform the differential expression analysis
