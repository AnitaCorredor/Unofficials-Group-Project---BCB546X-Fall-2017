# -Unofficials-Group-Project

# Utilized Journal Article
Regulatory modules controlling maize inflorescence architecture
Authors: Andrea L. Eveland, Alexander Goldshmidt, Michael Pautler, Kengo Morohashi, Christophe Liseron-Monfils, Michael W. Lewis, Sunita Kumari, Susumu Hiraga, Fang Yang, Erica Unger-Wallace, Andrew Olson, Sarah Hake, Erik Vollbrecht, Erich Grotewold, Doreen Ware, and David Jackson

# Data inspection of Figure2.A, 2.B and 2.C
To recreate Figure 2A, the supplementary table 2 was read to R, filtering out the differential expressed (DE) gene (by the column significant == "yes"). Depending on which mutant I chose ra1, ra2, or ra3 on the column q1 along with 1mm or 2mm on the column size with the “mut_series” on the column series. The gene_id were ppicked up as the character vector, which were then subjected to the package VennDiagram for plotting the Venn diagram stating the overlapping gene expression between ramosa mutants. 
To create Figure 2B, the workflow is similar but with an extra step, selecting out the transcription factor, performed priory. To select the transcription factors, grep the rows with the tag “transcription” by using Linux command lines on supplementary table 6. The transcription factors selected from table 6 were than processed through the following work flow mentioned above on R.
To reproduce the Figure 2C, the specific term for each category of GO enrichment (“transcription”, “nucleosome”, “chromatin”, and so on) were used to grep the interested rows on supplementary table 6, the selected genes were saved in corresponding files, which were then processed through R to pick up the same genes on supplementary table 2 for categorizing the genes with GO term. All the files of each category were then processed to pick up the overlapping DE genes across the mutants. The result was presented with the heat map creating by the package heatmap2 with the color key indicating the mean of the corrected P of each category set of DE genes. 

# Data inspection of Figure2.D and E
The data for differentially expressed (DE) across genes was provided by the authors in supplemental table 3, which contains information of the genes based on their across ra mutant backgrounds. 
To draw the figure 2D, we only need the information of 12 genes which stored at “test5.xlsx”. The ln fold change values were averages prior to plotting as a Heatmap.
Figures 2 E are two figures showing expression levels profile for two TF families: 13 TCP genes and 12 MADS-box TF family members. 
To drawn the Heatmap figures of the expression patterns for this families, we used the information obtained via subset function in R from Supplemental table2.
All the figures are drawn using R (version 3.3.2) with use of the packages 
library(readxl)
library(ggplot2)
library(reshape)
library(reshape2)
library(plyr)
library(scales)
updated to the latest version

# Data inspection of Figure3.A, B, D, and G

The data of expression signature across wild-type was provided by the authors in supplemental table 6, which contains 16,272 dynamically expressed genes based on their ex- pression profiles across wild-type libraries.

To draw the figures 3A, we only need the first columns 9 columns which stored at “expression_table_s6.csv”. The FPKM values were normalized to a Z-score scale prior to clustering. 

Figure3 B and D are two figure showing cluster 8 and cluster 11 expression pattern which could be obtained form above file via subset function in R

Figure3 G shows the expression level of genes in cluster 8 across ra mutant backgrounds. The fpkm data of wild type is obtained from table S6 and mutant’ expression data could be found in table S2.

All the figures are drawn using R (version 3.3.2) with all packages updated to the latest version (check Yan_Zhou_Figure3_A_to_C&G.Rmd).

# Data inspection of Figure3.C, E, and F

For the heat map for Figure 3C supplementary tables 6 & 7 are used to obtain cluster 11 gene id’s and significance in mutants for DE. However, natural log fold change values are not available. Therefore, gene id’s were utilized to pull these genes from Supplementary Table 5 and natural log fold change was calculated using R from values provided for wt of the mutant versus wt of the wild type. 

A similar procedure for figure 3E was utilized as explained for 3C, however only table 6 was used as supplementary table 7 is cluster 11 specific. For this figure, only those genes significantly differentially expressed in cluster 8 are included. Natural log fold changes were calculated in the same manner as for Figure 3C.

Similar to the previous two figures, figure 3F used supplementary tables 6 and 5 to identify significant DE in cluster 8 for ra1 mutants only and natural log fold changes are calculated for all mutants in the same manner as was previously stated for all mutants for that gene.

Data cleaning, organization, and figures are all done using R (version 3.3.3). For more information on specific code for Figures 3C, 3E and 3F please refer to Figures3CEF.Rmd.
