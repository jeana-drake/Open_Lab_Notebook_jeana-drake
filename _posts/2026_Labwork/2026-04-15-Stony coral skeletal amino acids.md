# Stony coral skeletal amino acids from the literature

## References

1. Young, Stephen D. "[Organic material from scleractinian coral skeletons—I. Variation in composition between several species](https://www.sciencedirect.com/science/article/pii/0305049171900678)" Comparative Biochemistry and Physiology Part B: Comparative Biochemistry 40.1 (1971): 113-120.

2. Mitterer, Richard M. "[Amino acid composition and metal binding capability of the skeletal protein of corals](https://www.ingentaconnect.com/content/umrsmas/bullmar/1978/00000028/00000001/art00012)" Bulletin of Marine Science 28.1 (1978): 173-180.

3. Goodfriend, Glenn A., P. E. Hare, and Ellen RM Druffel. "[Aspartic acid racemization and protein diagenesis in corals over the last 350 years](https://www.sciencedirect.com/science/article/pii/001670379290176J)" Geochimica et Cosmochimica Acta 56.10 (1992): 3847-3850.

4. Gautret, Pascale, Jean-Pierre Cruit, and André Freiwald. "[Composition of soluble mineralizing matrices in zooxanthellate and non-zooxanthellate scleractinian corals: biochemical assessment of photosynthetic metabolism through the study of a skeletal feature](https://link.springer.com/article/10.1007/BF02536884)" Facies 36.1 (1997): 189-194.

5. Cuif, J. P., et al. "[Biochemical markers of zooxanthellae symbiosis in soluble matrices of skeleton of 24 Scleractinia species](https://www.sciencedirect.com/science/article/pii/S1095643399000598?casa_token=nLvZ358COaYAAAAA:F3NEpthkzqh5ZXkTEgam2iEmPFrlA5kzzP_cmcA70wb-jnexg-awpiCGlspeeCkTIdKt6nYcNjY)" Comparative Biochemistry and Physiology Part A: Molecular & Integrative Physiology 123.3 (1999): 269-278.
  
6. Gupta, Lallan P., Atsushi Suzuki, and Hodaka Kawahata. "[Aspartic acid concentrations in coral skeletons as recorders of past disturbances of metabolic rates](https://link.springer.com/article/10.1007/s00338-006-0152-3)" Coral Reefs 25.4 (2006): 599-606.

7. Mass, Tali, et al. "[Aragonite precipitation by “proto-polyps” in coral cell cultures](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0035049)" PLoS One 7.4 (2012): e35049.

8. Tomiak, Peter J., et al. "[The role of skeletal micro-architecture in diagenesis and dating of Acropora palmata](https://www.sciencedirect.com/science/article/pii/S0016703716301399)" Geochimica et Cosmochimica Acta 183 (2016): 153-175.

9. Drake, unpublished, data collected 2018. Corals borrowed from Natural History Museum of Los Angeles County. AAR performed in Geochronology Lab at Northern Arizona University.

10. Drake, Jeana L., Julian P. Whitelegge, and David K. Jacobs. "[First sequencing of ancient coral skeletal proteins](https://www.nature.com/articles/s41598-020-75846-4)" Scientific reports 10.1 (2020): 19407.

11. Drake, Jeana, et al. "[Novel insights into conserved biomineralization mechanisms revealed from a cold-water scleractinian coral skeletal proteome](https://www.biorxiv.org/content/10.64898/2026.03.24.713908v1.abstract)" bioRxiv (2026): 2026-03.


### Extra Methods

1. Data from Gautret 1997 Figure 1 extracted in [WebPlotDigitizer](https://automeris.io/) from screenshots of each bar graph panel.


### Findings

1. Mass 2012 data removed as detections of several amino acids were reported as combined.
  
2. 7 amino acids used across all studies: Ala, Asx, Glx, Ile, Leu, Phe, Val.
  
3. Young 1971 %D+E consistently lower than other studies. Data removed.

4. Neighbor-joining tree (1000 bootstraps) on 7 amino acids in PAST5

<p align="center">
  <img src="https://github.com/jeana-drake/Open_Lab_Notebook_jeana-drake/blob/master/images/Stonycoral_7AA_NJtree.png?raw=true" />
</p>

5. nMDS on 7 amino acids in PAST5

<p align="center">
  <img src="https://github.com/jeana-drake/Open_Lab_Notebook_jeana-drake/blob/master/images/Stonycoral_7AA_nMDS.png?raw=true" />
</p>

6. %DE Boxplot in PAST5

<p align="center">
  <img src="https://github.com/jeana-drake/Open_Lab_Notebook_jeana-drake/blob/master/images/Stonycoral_7AA_boxplot.png?raw=true" />
</p>

7. Mann-Whitney test on %DE in PAST5, 1000 permutations
Complex	Robust
N:	20	N:	32
Mean rank:	12.615	Mean rank:	13.885

Mann-Whitney test for stochastic equality
U :	194
z :	2.3605	p (equal):	0.01825
Monte Carlo permutation:	p (equal):	0.0177

Vargha-Delaney A effect size:	0.6969 (medium)

Brunner-Munzel test for stochastic equality
phat :	0.30313	BM :	-2.4252
df :	30.488	p (equal):	0.021426
Monte Carlo permutation:	p (equal):	0.0232
