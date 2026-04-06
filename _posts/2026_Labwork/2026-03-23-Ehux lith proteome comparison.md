# Comparing coccolith proteomes between new and previously published dataset

## Datasets
1. Prada sequencing of Emiliania huxleyi CCMP1516 coccoliths at the Rutgers University [Biological Mass Spectrometry Facility](https://cabm.rutgers.edu/research/mass-spectrometry-facility) after cleaning and extraction following protocols found in the BECORAL Protocols subfolder. Unpublished data.

2. [Skeffington et al. 2023](https://www.nature.com/articles/s41467-023-39336-1) sequencing of Emiliania huxleyi AWI1516 coccoliths. This strain is maintained at the Alfred Wagner Institute and is derived from CCMP1516.


## Procedure

### 20260406

1. Skeffington acidic lith proteins run through DeepTMHMM 1.0.


### 20260402

1. Skeffington acidic lith proteins run through NetOGlyc 4.0.


### 20260401

1. Skeffington acidic proteins (n = 15) - defined as >15.5% D+E and pI < 4.5 per [Desmophyllum skeleton proteome work](https://www.biorxiv.org/content/10.64898/2026.03.24.713908v1.abstract).

2. NetNGlyc 1.0 for N-linked glycosylation prediction. Only retain jury agreement of 9/9 predictions. Only extracellular N-glyc sites to be retained (based on TMHMM).

3. NetOGlyc 4.0. Use default cutoffs.
