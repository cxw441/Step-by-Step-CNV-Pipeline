# Step-by-Step-CNV-Pipeline


STEP 1: Base calling and Quality Control (QC) 

o   Most high throughput sequencers generate output in FastQ format.  

o   Raw data reads – .fastq (uncompressed) or .fastq.gz (compressed)

| Platform      |  Basecall File Format           | Basecaller |
| ------------- | --------------------------------| ---------- |
| Illumina      | Binary Base Call (BCL)          |            |
| PacBio        | Basecall File (bash.h5/bax.h5)  |            |
| ONT           | FASTQ                           | Dorado     |

o   Dorado is a basecaller for Oxford Nanopore Technology (ONT) reads

o   Base quality (BQ) score = Phred score. Base quality is important for variant calling.

o   Q20 and higher is generally a good score.

o   QC tool 

    - FASTQC is a quality control tool for high throughput sequence data.
    - It is written in Java.
    - http://www.bioinformatics.babraham.ac.uk/projects/fastqc/
    - MultiQC is used to aggregate results from multiple FastQC runs into one single html report

| Platform             | QC                           |
| -------------------- | -----------------------------|
| ONT                  | NanoQC                       |


STEP 2: Trimming 

o   Involves removal of poor quality reads and trim adapter sequences 

o   Trimming tool

    - http://www.usadellab.org/cms/?page=trimmomatic

| Platform             | Tool                         |
| -------------------- | -----------------------------|
| Illumina             | BBduk or Cutadapt            |
| ONT                  | Porechop                     |


STEP 3: Mapping or Alignment 

o   .sam – sequence alignment map; .bam – binary alignment map; .cram – reference based compressed alignment map

o   Mapping quality (MQ) is a phred-score of the quality of the alignment

o   Mapping methods

| Burrows-Wheeler      | Hashing                      |
| -------------------- | -----------------------------|
| BWA, Bowtie          | Stampy                       |

o   Mapping tools

| Platform             | Tool                         |
| -------------------- | -----------------------------|
| Illumina             | BWA MEM                      |
| ONT                  | Minimap2                     |

o   Post-mapping data QC tools

    - Qualimap 

STEP 4: Variant calling


























