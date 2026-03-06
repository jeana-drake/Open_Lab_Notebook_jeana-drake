# February/March 2026 Multi-Coral Proteomics Analysis

## Corals
1. Acropora digitigera: Takeuchi, Takeshi, et al. "[Stepwise evolution of coral biomineralization revealed with genome-wide proteomics and transcriptomics](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0156424)." PLoS One 11.6 (2016): e0156424.

2. Acropora millepora: Ramos-Silva, Paula, et al. "[The skeletal proteome of the coral Acropora millepora: the evolution of calcification by co-option and domain shuffling](https://academic.oup.com/mbe/article/30/9/2099/998666?cited-by=yesl30/9)." Molecular Biology and Evolution 30.9 (2013): 2099-2112.

3. Oculina patagonica: Zaquin, Tal, et al. "[Different skeletal protein toolkits achieve similar structure and performance in the tropical coral Stylophora pistillata and the temperate Oculina patagonica](https://www.nature.com/articles/s41598-022-20744-0)." Scientific Reports 12.1 (2022): 16575.
  
4. Stylophora pistillata: Drake, Jeana L., et al. "[Proteomic analysis of skeletal organic matrix from the stony coral Stylophora pistillata](https://www.pnas.org/doi/abs/10.1073/pnas.1301419110)." Proceedings of the National Academy of Sciences 110.10 (2013): 3788-3793.

5. Stylophora pistillata: Peled, Yanai, et al. "[Optimization of skeletal protein preparation for LC–MS/MS sequencing yields additional coral skeletal proteins in Stylophora pistillata](https://link.springer.com/article/10.1186/s42833-020-00014-x)." BMC Materials 2.1 (2020): 8.

6. Stylophora pistillata: Mummadisetti, Manjula P., Jeana L. Drake, and Paul G. Falkowski. "[The spatial network of skeletal proteins in a stony coral](https://royalsocietypublishing.org/rsif/article/18/175/20200859/89834)." Journal of The Royal Society Interface 18.175 (2021).

7. From the T. Mass lab by Tal Zaquin: Astrangia poculata, Balanophylia europa, Leptopsammia pruvoti, Lobactis scutaria, Montipora capitata, Oculina patagonica, Phyllangia amouchezii, Pocillopora damicornis, Porites astreoides, Porites lobata

## Analyses

### 20260303
1. Make SOM peptides non-redundant (nr) tabl of accession numbers and peptides only

2. Make All-SOM Proteins file

3. Merge nr peptides and all proteins files in R
newtable <- merge(DFprot, DRpep, by.x = c(ProtAccessCol), by.y = c(PepAccessCol), all = TRUE)

4. Map peptides to proteins in R
PepMap <- find.peptide(data = newtablefrom3, protein_sequence = ProtCol, peptide_sequence = PepCol)

5. Remove rows where peptides not mapped

6. Write excel equations for consecutive peptides, 1 aa apart, 2 aa's apart, 3 aa's apart


### 20260326
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


#20260302
1. Pull all contatonated pseudoproteins (with x's) that cluster to at least 2 sequences. Yields 37 clusters of 501 sequences.

2. Blast2GO: blastp_fast, nr, no filter, e^-10


#20260303
1. 500 sequences fuly ran through blast-p in Blast2GO. 1 sequence didn't run = 9298 aa long

2. Run Interpro scan


#20260304
1. Merge IntroPro scan to Annotation

2. Map GO terms with default

3. Run Annotation with defaults, e^-6

4. Save output as .b2g and export as. txt

5. Reblast missing long Pdam sequence - still fails. Blast-p in NCBI. Had GO terms from first Blast2GO run.


#20260305, 20260306
1. MSA on clusters 0, 6, 8, 11, 12

2. ClustalO online

3. Split clusters 6, 8, 11 into 1-60 aa, 61-120 aa, and >120 aa lengths for alignment
