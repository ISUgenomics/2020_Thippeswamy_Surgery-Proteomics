# Methods:

 Analysis was performed by the R package MethaboanalystR 2.0 (Chong, et. al., 2019) that contains R functions and libraries underlying MetaboAnalyst web server (Chong, et. al., 2018) was used for data analysis. Upon finding data integrity to be satisfactory (no peptide with more than 50% missing replicates, positive values for the area), missing value estimation was imputed using Singular Value Decomposition (SVD) method. Non-informative values that were near-constant throughout the experiment conditions were detected using interquantile range (IQR) estimation method and were deleted. Data was normalized using Quantile normalization method. Data transformation was performed based on Generalized logarithm transformation ( glog) to make individual features more comparable. The control and treatment samples were compared by t-test with the adjusted P- value (FDR) cutoff of 0.01. Fold change (FC) analysis with threshold of 2 was performed to compare the absolute value of change between control and treatment values. A volcano plot was created to combine the Fold change and the t-test analysis.  The PCA analysis was performed using the prccomp package and pairwise score plots were created to provide an overview of the various separation patterns among the most significant components. Partial least squared (PLS) regression was then performed using the plsr function provided by R pls package to predict the continuous and discrete variables. A PLS-DA model was built to classify and cross-validate PLS using the caret package.
The uniport protein ids that were up/down regulated  with the P -values less than 0.01  were used to retrieve the corresponding KEGG ids using the “Retrieve/ID mapping” tool of UniProt (accessible at http://www.uniprot.org/uploadlists/). KEGG ids were then used to retrieve biological pathway association of the proteins. Enrichment analysis was performed using The Database for Annotation, Visualization and Integrated Discovery (DAVID) 6.8 Tools (Huang, et. al., 2009).

One-way Analysis of Variance (ANOVA) has been performed. Fisher’s least significant difference method (Fisher’s LSD) was used to identify which two levels are different.


•	J. Chong, M. Yamamoto, and J. Xia; MetaboAnalystR 2.0: From Raw Spectra to Biological Insights: *Metabolites*, (2019), **9.3**: 57-67.

•	 J. Chong , O. Soufan, C. Li, I. Caraus, S. Li, G. Bourque, D. S. Wishart, J. Xia; MetaboAnalyst 4.0: towards more transparent and integrative metabolomics analysis: *Nucleic Acids Research*, (2018), **46**: W486–W494.

•	D. W. Huang , B. T. Sherman , RA. Lempicki; Systematic and integrative analysis of large gene lists using DAVID Bioinformatics Resources, *Nature Protoc.*, (2009), **4**: 44-57.

•	D. W. Huang, B. T. Sherman,R. A. Lempicki; Bioinformatics enrichment tools: paths toward the comprehensive functional analysis of large gene lists,  *Nucleic Acids Res.*, (2009), **37**: 1-13.
