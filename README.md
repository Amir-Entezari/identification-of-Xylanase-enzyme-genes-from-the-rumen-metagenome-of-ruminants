# Xylanase Gene Identification from Metagenomic Data

## Overview
This repository contains a bioinformatics pipeline for identifying potential xylanase genes from the metagenome of ruminant rumen microbiota. The project employs a combination of sequence alignment, clustering, and conserved domain analysis to detect and analyze xylanase sequences.

## Features
- **BLAST-based Sequence Search**: Identification of potential xylanase sequences from metagenomic contigs.
- **Sequence Clustering with CD-HIT**: Removal of redundancy to select representative sequences.
- **Conserved Domain Analysis**: Multiple sequence alignment and hidden Markov models (HMM) for identifying conserved regions.
- **PSSM-based Refinement**: PSI-BLAST-based iterative filtering of sequences to enhance specificity.

## Steps
### Step 1: Identifying Potential Xylanase Sequences
- Install and configure `BLAST+`.
- Download reference thermostable xylanase sequences.
- Perform BLAST search on metagenomic contigs.
- Extract significant hits based on sequence similarity.

### Step 2: Clustering and Representative Selection
- Cluster highly similar sequences using `CD-HIT` (97% similarity threshold).
- Extract representative sequences from each cluster (longest sequence preferred).

### Step 3: Building a Conserved Domain Model and Filtering
- Perform multiple sequence alignment using `Clustal Omega`.
- Construct a conserved domain model using `HMMER`.
- Generate a Position-Specific Scoring Matrix (PSSM) using `PSI-BLAST`.
- Filter sequences using profile HMM search and PSI-BLAST results.

## Installation
To run this pipeline, install the required bioinformatics tools:

```sh
conda install -c bioconda blast diamond cd-hit clustalo hmmer
pip install biopython gdown seqkit matplotlib pandas
```

## Data Sources
- Metagenomic contigs: Provided dataset from ruminant microbiota.
- Reference xylanase sequences: Downloaded from public databases.

## Output Files
- `step1/blast_results.txt`: Raw BLAST search results.
- `step2/clustered_xylanase.fasta`: Clustered non-redundant sequences.
- `step2/representative_sequences.fasta`: Selected representative sequences.
- `step3/xylanase.pssm`: Position-Specific Scoring Matrix.
- `step3/conserved_xylanase.hmm`: Hidden Markov Model of xylanase.


## Acknowledgments
This project was completed under the guidance of the Professor Kavousi, Professor Fotouhi, and professor Montazeri at the University of Tehran.

