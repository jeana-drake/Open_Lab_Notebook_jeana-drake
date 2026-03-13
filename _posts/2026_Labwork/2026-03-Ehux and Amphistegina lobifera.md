### Coccolithophore Lith and Foram Test SOM Proteomics

# Emiliania huxleyi (unpublished)
1. From F. Prada post-doc with Falko.
  
2. Classify SOM proteins according to Desmophyllum pertusum functional groups (annotation and GO analysis in Blast2GO).

3. Amino acid quantification in R with AAcount command in Biostrings package.

4. pI calculation in R with pI command in Peptides package.

5. Graph as pie chart in R with same categories and colors as D. pertusum manuscript.


# Amphistegina lobifera
1. From [Prada et al. 2024 PNAS](https://www.pnas.org/doi/abs/10.1073/pnas.2417845121)

2. Classify SOM proteins according to Desmophyllum pertusum functional groups (annotation and GO analysis in Blast2GO).

3. Amino acid quantification in R with AAcount command in Biostrings package.

4. pI calculation in R with pI command in Peptides package.

5. Graph as pie chart in R with same categories and colors as D. pertusum manuscript.


# 20260312
1. Use January 2026 Blast2GO against primates to identify potential contaminants in list of 290 Ehux lith proteins.

2. 4 were missing from January 2026 list. Run in Blast2GO, blastp_fast, taxonomy filter = primates (taxa 9443), e-10

3. Run 3 of missing sequences with Blast2GO hits in NCBI, blastp_nr, against Homo sapiens

4. Yiels 269 non-contaminant coccolith proteins.


# 20260313
1. Pull [Skeffington 2023 Nature Communications](https://www.nature.com/articles/s41467-023-39336-1) coccolith, vesicle, and coccosphere proteins from Supplementary Documents SI 2, 3, 4

2. Blast-p in NCBI: Prada Ehux lith proteins against three Skeffington SI files; e better than -50, similarity >75%, and >100 amino acids

3. Compare with Functional Classifications of Prada Ehux lith proteins
