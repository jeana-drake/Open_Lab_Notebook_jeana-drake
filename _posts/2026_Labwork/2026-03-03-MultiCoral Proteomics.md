# February/March 2026 Multi-Coral Proteomics Analysis

## Corals
1. Acropora digitigera: Takeuchi, Takeshi, et al. "[Stepwise evolution of coral biomineralization revealed with genome-wide proteomics and transcriptomics](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0156424)." PLoS One 11.6 (2016): e0156424.

2. Acropora millepora: Ramos-Silva, Paula, et al. "[The skeletal proteome of the coral Acropora millepora: the evolution of calcification by co-option and domain shuffling](https://academic.oup.com/mbe/article/30/9/2099/998666?cited-by=yesl30/9)." Molecular Biology and Evolution 30.9 (2013): 2099-2112.

3. Oculina patagonica: Zaquin, Tal, et al. "[Different skeletal protein toolkits achieve similar structure and performance in the tropical coral Stylophora pistillata and the temperate Oculina patagonica](https://www.nature.com/articles/s41598-022-20744-0)." Scientific Reports 12.1 (2022): 16575.
  
4. Stylophora pistillata: Drake, Jeana L., et al. "[Proteomic analysis of skeletal organic matrix from the stony coral Stylophora pistillata](https://www.pnas.org/doi/abs/10.1073/pnas.1301419110)." Proceedings of the National Academy of Sciences 110.10 (2013): 3788-3793.

5. Stylophora pistillata: Peled, Yanai, et al. "[Optimization of skeletal protein preparation for LC–MS/MS sequencing yields additional coral skeletal proteins in Stylophora pistillata](https://link.springer.com/article/10.1186/s42833-020-00014-x)." BMC Materials 2.1 (2020): 8.

6. Stylophora pistillata: Mummadisetti, Manjula P., Jeana L. Drake, and Paul G. Falkowski. "[The spatial network of skeletal proteins in a stony coral](https://royalsocietypublishing.org/rsif/article/18/175/20200859/89834)." Journal of The Royal Society Interface 18.175 (2021).

7. From the T. Mass lab by Tal Zaquin: Astrangia poculata, Balanophylia europa, Leptopsammia pruvoti, Lobactis scutaria, Montipora capitata, Oculina patagonica, Phyllangia amouchezii, Pocillopora damicornis, Porites astreoides, Porites lobata

8. Desmophyllum pertusum: Drake, Jeana L., et. al. "[Novel insights into conserved biomineralization mechanisms revealed from a cold-water scleractinian coral skeletal proteome](https://www.biorxiv.org/content/10.64898/2026.03.24.713908v1.abstract)" bioRxiv (2026)/in review.

9. Orbicella annularis: Drake, Jeana L., Julian P. Whitelegge, and David K. Jacobs. "[First sequencing of ancient coral skeletal proteins](https://www.nature.com/articles/s41598-020-75846-4)" Scientific reports 10.1 (2020): 19407.


## Analyses

### 20260423 to 20260427

1. New corals sent by Hollie Putnam: Pocillopora tuahiniensis, Pocillopora meandrina, Pocillopora verrucosa, Pocillopora grandis, Pocillopora acuta, Porites compressa, Acropora pulchra, Pocillopora compressa, Cladocora caespitosa

2. Run via Data Independent Acquisition protocol at CABM Biological Mass Spectrometry Facility.

3. Pivot Table filters: Contaminant, EG Pep<0.01, EG Qvalue<0.01

4. Pivot Table column: R.Condition

5. Pivot Table rows: PG.ProteinGroups (lead), PEP.StrippedSequence, PEP.RunEvidenceCount, ProteinName (added to full data worksheet; is copy of PG.ProteinGroups)

6. Add Sort worksheet. Copy/PasteSpecial -> Values of PivotTable without GrandTotal.

7. Sort by ProteinNames and then by PEP.RunEvidenceCount. Delete rows with 'peptide sequenceTotal' and PEPrunevidencecount 'value Total'. Delete rows with contaminants mixed with target hits. Leaves rows with peptide sequence, run evidence count, protein name, PEP.Quantity (as R.Condition). For test file 'MS6747_HT_DIA_Spectronaut_Protein_ID_34 - CC3_PTM.xlsx' yields target-only 6749 peptide hits for Cladocora caespitosa.

8. Add column 2PLUSPeps1 as E=IF(D2=D3, "SAME", "different"). Copy/PasteSpecial -> Values. SAME means that present row has same Protein ID as row below it.

9. Add column 2PLUSPeps2 as F=IF(D2=D1, "SAME", "different"). Copy/PasteSpecial -> Values. SAME means that present row has same Protein ID as row above it.

10. Add column SinglePep as G=IF(AND(E="different", "different"), "SINGLEPEP", "NA". Copy/PasteSpecial -> Values. SINGLEPEP means that the Protein ID in the present row has only a single peptide detected.

11. Add column SinglePep5 as =IF(AND(G="SINGLEPEP", B>1), "SINGLEPEP2", "no". Copy/PasteSpecial -> Values. SINGLEPEP2 means that the Protein ID in the present row has a single peptide detected at least 2 times.

13. Add column KEEP as =IF(OR(G="NA", H="SINGLEPEP2"), "KEEP", "-". Copy/PasteSpecial -> Values. KEEP means that the Protein ID in the present row has multiple peptides detected or a single peptide detected at least 2 times.

14. Sort worksheet by Keep (Z to A), then ProteinNames (A to Z), then PEP.RunEvidenceCount (decreasing).

15. Add Keep worksheet. Copy/Paste all sorted rows with KEEP designation. For test file 'MS6747_HT_DIA_Spectronaut_Protein_ID_34 - CC3_PTM.xlsx' yields target-only 6242 peptide hits with multiple peps per protein or at least two spectra for single-peptide protein hits for Cladocora caespitosa.

16. Add cell with J=COUNTIF(E2:E10000, "different"). For file 'MS6747_HT_DIA_Spectronaut_Protein_ID_34 - CC3_PTM.xlsx' yields 865 proteins detected with two individual peptides or one peptides with at least 2 spectra above cutoffs.

17. Repeat for MS6747_HT_DIA_Spectronaut_Protein_ID_18-20 - Pocillopora grandis_PTM.xlsx. Yields 4289 target-only peptides.

18. If species has multiple replicates, add the following steps:

19. After 2PLUSPeps1 and 2PLUSPeps2, add column of SameRun as =IF(OR(F="SAME", G="SAME"),"SAMERUN","singlepep"). SAMERUN means there are 2+ unique peptides in the same replicate run. Copy/PasteSpecial -> Values. 

20. After SameRun, add column of CrossRun as =IF(AND(D>1, E>1),"CROSSRUN","singlerun"). If triplicate samples were processed and run individually for the same species, add a column of 2OF3 as =IF((D>1, E>1, F>1)>=2,"CROSSRUN","singlerun"). CROSSRUN means the peptide was detected in at least two replicate runs. Copy/PasteSpecial -> Values. 

21. Add column of SingleRunSinglePep as =IF(AND(SameRun="singlepep", B>1),"SINGLERUN2","no". Copy/PasteSpecial -> Values. SINGLERUN2 means the Protein ID in this row has one peptide detected at least 2 times in the same replicate.

22. Add column of KeepSingle as =IF(OR(SingleRunSinglePep2="SINGLERUN2", AND(F="different", G="different", CrossRun="different")),"KEEP","-"). KEEP means the Protein ID in this row has a peptide that was *either* detected at least twice in the same run or across at least two replicates.

23. Add column of KeepFinal as =IF(OR(SameRun="SAMERUN", KeepSingle="KEEP"),"KEEP","-"). KEEP means the Protein ID in this row has multiple unique peptides detected in one replicate run, only one peptide detected in only one run but detected at least twice, or only peptide detected in each replicate run but detected in at least 2 runs.

24. Copy/PasteSpecial -> Values for all remaining formula rows.

25. Sort by the KeepFinal column for KEEP, then by ProteinName, then by PEP.RunEvidenceCount.

### 20260410 to 2026041
1. Check multi-coral proteomics SOMP lists for likely human contaminants

2. Astrangia poculata, Balanophyllia europa, Leptopsammia provuti, Lobactis scutaria, Montipora capitata, Oculina patagonica, Pocillopora damicornis, Porites astreoides, Porites lobata

3. Blast2GO against NCBI_nr primates.

4. Check alignments of high scoring Blast2GO matches in NCBI blastp.

### 20260403

1. Order Orbicella annularis (modern) peptides based on start location, transpose, concatonate

2. Remove overlaps and make peps consecutive up to 3 x's, remove extra x's at ends. Yields 34 proteins

### 20260402

1. Orbicella annularis (modern), trypsin followed by GluC digestion, separate soluble and insolube runs

2. Peptide-level Mascot files sent from UCLA's Pasarow Lab: 18681, 18688, 18694, 18711

3. Combined peptide data from all 4 files, make peptides non-redundant per protein

4. In R: match peptides to whole proteins (merge and find_peptide) and location of peptides within each protein (setDT)
   

### 20260317

1. Finish cleaning up Desmophyllum pertusum concatonation - remove overlaps, make peps consecutive up to 3 x's, remove extra x's at ends. Yields 382 proteins.

2. Add peps and sequences to multi-coral proteomics .xlsx and .fasta files.
   

### 20260311

1. Pocillopora grandis genome .gff3 output file in Braker3 converted to CDS in GFFreadtool in Galaxy

2. P grandis BUSCO analysis
   

### 20260310

1. Desmophyllum pertusum peptides from MS6036

2. Sort, remove redundant peptides

3. setDT command in R to match peptides to detected proteins

4. merg and find_peptide commands in R to map nr peptides to detected proteins

5. Concatonate and edit


### 20260309

1. Convert Pocillopora grandis genome in NCBI [GCA_96402706.2](https://www.ncbi.nlm.nih.gov/datasets/genome/GCA_964027065.2/) .fna file to predicted protein file in Galaxy. No predicted protein file in NCBI.

2. Predicted protein file for model file:
      a. P. damicornis genome file ([GCF_003804095.1[(https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_003704095.1/), from RSMAS) has too-low scaffold N50 and too-high scaffold L50.
     b. P. verrucosa genome file ([GCF_036669915.1](https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_036669915.1/), State Key Lab for Bioelectronics) has good scaffold N50 and L50. Use this one.
     c. Pver has only 84 proteins in UniProt; Pdam has 30k proteins in UniProt but is based on RSMAS genome above.

3. Run Pgrand .fna file in Braker3 in Galaxy using Pver NCBI predicted protein file as a guide.

4. Pocillopora tuahiniensis is sister to P. verrucosa but is in a different clade than P. meandrina [Johnston & Burgess 2023 Zootaxa](https://mapress.com/zt/article/view/zootaxa.5369.1.5).

5. Checked NCBI, reefgenomics.org, marinegenomics.oist.jp, and Google Scholar for P. tuahiniensis genome or transcriptome. None found. Must combine P. dam, P. ver, P. acuta, P. grandis, and P. meandrina predicted protein files.


### 20260305, 20260306

1. MSA on clusters 0, 6, 8, 11, 12

2. ClustalO online

3. Split clusters 6, 8, 11 into 1-60 aa, 61-120 aa, and >120 aa lengths for alignment


### 20260304

1. Merge IntroPro scan to Annotation

2. Map GO terms with default

3. Run Annotation with defaults, e^-6

4. Save output as .b2g and export as. txt

5. Reblast missing long Pdam sequence - still fails. Blast-p in NCBI. Had GO terms from first Blast2GO run.


### 20260303

1. 500 sequences fuly ran through blast-p in Blast2GO. 1 sequence didn't run = 9298 aa long

2. Run Interpro scan
   
3. 1. Make SOM peptides non-redundant (nr) tabl of accession numbers and peptides only

4. Make All-SOM Proteins file

5. Merge nr peptides and all proteins files in R
newtable <- merge(DFprot, DRpep, by.x = c(ProtAccessCol), by.y = c(PepAccessCol), all = TRUE)

6. Map peptides to proteins in R
PepMap <- find.peptide(data = newtablefrom3, protein_sequence = ProtCol, peptide_sequence = PepCol)

7. Remove rows where peptides not mapped

8. Write excel equations for consecutive peptides, 1 aa apart, 2 aa's apart, 3 aa's apart


### 20260302

1. Pull all contatonated pseudoproteins (with x's) that cluster to at least 2 sequences. Yields 37 clusters of 501 sequences.

2. Blast2GO: blastp_fast, nr, no filter, e^-10


### 20260226

1. Order peptides within proteins

2. Write excel equation to concatonate with 10 x's between non-consecutive peptides

3. Write equations to find consecutive, 1 aa apart, 2 aa's apart, 3 aa's apart. Manually reset

4. Convert to fasta format

5. Yieelds 600 total pseudo proteins of contatonated detected peptides

6. CD-Hit for 90% sim, 75% sim

7. 50% sim fails in CD-Hit. Set -n = 2 for shortest word length allowed

8. 60% works, 50% works, 40% works

9. 30% fails

10. Remove all x's from contatonated pseudoproteins. CD-Hit

11. 90%, 75% work. Same clusters as with x's

12. CD-Hit on whole proteins for 600 peptide-mapped proteins

13. 75% works

14. 50% works with -n = 3

15. 30%, 40% fail even with -n = 2
