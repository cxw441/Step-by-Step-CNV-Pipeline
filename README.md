# Step-by-Step-CNV-Pipeline

Step 1: Base calling and Quality Control (QC) 

o   Most high throughput sequencers generate output in FastQ format.  

o   Raw data reads – .fastq (uncompressed) or .fastq.gz (compressed)

| Platform      |  Basecall File Format         | Basecaller |
| ------------- | ------------------------------| ---------- |
| Illumina      | Binary Base Call (BCL)        |
| PacBio        | Basecall File (bash.h5/bax.h5)|
| ONT           | FASTQ                         | Dorado     |

o   Dorado is a basecaller for Oxford Nanopore Technology (ONT) reads

o   Base quality (BQ) score = Phred score. Base quality is important for variant calling.

o   Q20 and higher is generally a good score.

o   QC tool 
    - FASTQC is a quality control tool for high throughput sequence data.
    - It is written in Java.
    - http://www.bioinformatics.babraham.ac.uk/projects/fastqc/
    
Step 2: Trimming 

o   
