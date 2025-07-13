# illumina-genome-assembly-annotation 🧬

This script performs an end-to-end workflow for processing Illumina paired-end reads, assembling bacterial genomes, and annotating them. It includes quality control, trimming, assembly, polishing, evaluation, and annotation steps.

## 🔁 Workflow Overview

1. **Quality control**: FastQC + MultiQC
2. **Read trimming**: Trimmomatic with adapter removal
3. **Genome assembly**: SPAdes
4. **Assembly polishing**: Pilon
5. **Assembly evaluation**: QUAST (with optional reference)
6. **Annotation**: Prokka

## 📁 Directory Structure

- `data/`: Raw Illumina reads (`*_R1.fastq.gz`, `*_R2.fastq.gz`)
- `trimmed_reads/`: Trimmed reads output
- `spades_output/`: Raw SPAdes assembly folders
- `draft_assemblies/`: Extracted contigs from SPAdes output
- `pilon_output/`: Polished assemblies with Pilon
- `quast_results/`: Quality reports from QUAST
- `annotation/`: Genome annotation results from Prokka

## ⚙️ Requirements

- fastqc
- multiqc
- trimmomatic
- spades
- bwa
- samtools
- pilon
- quast
- prokka

These can be installed via conda:
```bash
conda create -n genome_pipeline_env -c bioconda -c conda-forge \
    fastqc multiqc trimmomatic spades bwa samtools pilon quast prokka
conda activate genome_pipeline_env
```

## 🚀 Running the Pipeline

Make sure your input data is in the `data/` folder and named like:
```
sample1_R1.fastq.gz
sample1_R2.fastq.gz
```

Then run:
```bash
bash genome_pipeline.sh
```

## 📌 Notes

- Edit the `REFERENCE="reference.fasta"` variable in the script if you have a reference genome for QUAST.
- Update the path to your adapter file: `TruSeq3-PE.fa`.

## 👨‍🔬 Author

**Abraham Espinoza Culupú**  
Molecular biologist focused on microbial genomics and antimicrobial resistance.

## 📄 License

MIT License
