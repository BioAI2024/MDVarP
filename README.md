===============================================================================
MDVarP version 1.0 2-20-2024

The MDVarP implements an ensemble model based on 1000 random forest predictors 
to identify combinations of modifier variants and disease-causing variants. 

The MDVarP was built under R version 4.0.2.

===============================================================================
Executable code:
------------------------------------------------------------------------------
The executable R script, i.e. MDVarP.r, is in the MDVarP.v1.0/ directory.

===============================================================================
Use MDVarP:
------------------------------------------------------------------------------
 
Run shell scripts in Windows.

1. Set path
set R_Script= Your Rscript PATH
#eg:   
#set R_Script="C:\Program Files\R\R-4.0.2\bin\RScript.exe"

2. Run MDVarP
%R_Script% MDVarP.r inputfile outputfile

3. One example of command line:
%R_Script% MDVarP.r test_data.txt test_pred.tsv 

===============================================================================
Input format:
------------------------------------------------------------------------------

The input file contains 1 line per variant pair.  There are 66 columns:

#Column	Feature	Description
1	Bi_Loci_ID	Locus_1-Locus_2-Gene_1-Gene_2
2	3prime_utr_1	The 2nd column to the 15th column: VEP consequence for locus_1. Vaule = 1 or 0. 1 stands for Yes, 0 stands for No.
3	5prime_utr_1	
4	Canonical_splice_1	
5	Downstream_1	
6	Intergenic_1	
7	Intronic_1	
8	Noncoding_change_1	
9	Non_synonymous_1	
10	Regulatory_1	
11	Splice_site_1	
12	Stop_gained_1	
13	Stop_lost_1	
14	Synonymous_1	
15	Upstream_1	
16	3prime_utr_2	The 16th column to the 29th column: VEP consequence for locus_2. Vaule = 1 or 0. 1 stands for Yes, 0 stands for No.
17	5prime_utr_2	
18	Canonical_splice_2	
19	Downstream_2	
20	Intergenic_2	
21	Intronic_2	
22	Noncoding_change_2	
23	Non_synonymous_2	
24	Regulatory_2	
25	Splice_site_2	
26	Stop_gained_2	
27	Stop_lost_2	
28	Synonymous_2	
29	Upstream_2	
30	Hmmpanther_1	The 30th column to the 35th column: Domain annotation inferred from VEP annotation for locus 1.1/0 for coding loci. '.' for non-coding loci.
31	Lcompl_1	
32	Ncoils_1	
33	Ndomain_1	
34	Sigp_1	
35	Other_1	
36	Hmmpanther_2	The 36th column to the 41th column: Domain annotation inferred from VEP annotation for locus 2.1/0 for coding loci. '.' for non-coding loci.
37	Lcompl_2	
38	Ncoils_2	
39	Ndomain_2	
40	Sigp_2	
41	Other_2	
42	priPhyloP_1	Primate PhyloP score of locus 1.
43	mamPhyloP_1	Mammalian PhyloP score of locus 1.
44	verPhyloP_1	Vertebrate PhyloP score of locus 1.
45	priPhyloP_2	Primate PhyloP score of locus 2.
46	mamPhyloP_2	Mammalian PhyloP score of locus 2.
47	verPhyloP_2	Vertebrate PhyloP score of locus 2.
48	CADD_Phred_1	CADD score of locus 1. Scaled C-score ranking a variant relative to all possible substitutions of the human genome
49	CADD_Phred_2	CADD score of locus 2. Scaled C-score ranking a variant relative to all possible substitutions of the human genome
50	Pi_1	Nucleotide diversity of loucs 1.
51	FST_1	Fixation index of population differentiation of locus 1.
52	HWE_1	Hardy-Weinberg equilibrium p value of locus 1.
53	DAF_1	Derived allele frequency of locus 1.
54	Pi_2	Nucleotide diversity of loucs 2.
55	FST_2	Fixation index of population differentiation of locus 2.
56	HWE_2	Hardy-Weinberg equilibrium p value of locus 2.
57	DAF_2	Derived allele frequency of locus 2.
58	Recessive_Pvalue_1	Gene_1. Predicted probability of recessive disease causation for the protein-coding genes
59	Haploinsufficiency_Pvalue_1	Gene_1. Gene-based probability of exhibiting haploinsufficiency.
60	Haploinsufficiency_HGIS_1	Gene_1. Genome-wide haploinsufficiency score
61	Recessive_Pvalue_2	Gene_2. Predicted probability of recessive disease causation for the protein-coding genes
62	Haploinsufficiency_Pvalue_2	Gene_2. Gene-based probability of exhibiting haploinsufficiency.
63	Haploinsufficiency_HGIS_2	Gene_2. Genome-wide haploinsufficiency score
64	Physical_interaction	Vaule = 1 or 0. 1 stands for Yes, 0 stands for No.
65	Giant_interaction	Vaule = 1 or 0. 1 stands for Yes, 0 stands for No.
66	Biological_distance	Value

===============================================================================
Output format:
------------------------------------------------------------------------------

The output file contains 1 line per variant pair.  There are 4 columns:
1 Bi_Loci_ID
2 C-score
3 S-score
4 MDVarP_output # 1 for “Associated-pair”, 0 for “Nonrelevant-pair”
