# damage
Estimate nucleobase damage from sequencing statistics and substitution artifacts

## Quick Start

Grab the code, install the dependencies using conda, download a sample Illumina sequencing read set (murine hepatitis virus) from the NCBI short read archive, then run the damage command.

```shell
git clone https://github.com/nodrogluap/damage
cd damage
conda env create -f damage.yml
conda activate damage
wget https://sra-pub-sars-cov2.s3.amazonaws.com/sra-src/SRR18026714/MHV-t0-1_S1_L001_R1_001.fastq.gz.1 -O test_r1.fastq.gz
wget https://sra-pub-sars-cov2.s3.amazonaws.com/sra-src/SRR18026714/MHV-t0-1_S1_L001_R2_001.fastq.gz.1 -O test_r2.fastq.gz
./damage test/MHV-A59-B11.fasta test_r1.fastq.gz test_r2.fastq.gz > test_results.txt
```

The contents of test_results.txt should look something like this:

```
Observed majority C positions	5610
Observed majority G positions	7473
% reads mapping	16.019786451107
Median insert size for paired reads: 247
Median % G->T in oxoG contexts	0
Mean % G->T in oxoG contexts	0.060335051410812
Median % G->T in non-oxoG contexts	0
Mean % G->T in non-oxoG contexts	0.0664530019607484
Median % C->T in UV lesion contexts	0
Mean % C->T in UV lesion contexts	0.0628477938171278
Median % C->T in non-UV lesion contexts	0
Mean % C->T in non-UV lesion contexts	0.0801748317862073
```
