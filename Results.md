# Results

## Normalization

Considering the vast dynamic range of biosample features, in this case  
Effect of normalization on the abundance distribution has been shown in the following figures. data is normalized using the quantile normalization method and log transformed using Generalized log transformation function (glog) function in R.   

* ###  KA-NoSurgery vs. KA-Surgery

![norm](assets/norm_KA-NoS-KA-S.png)

![snorm](assets/snorm_KA-NoS-KA-S.png)

* ### KA-NoSurgery vs. Vehicle-NoSurgery

![norm](assets/norm_KA-NoS-Vehicle-NoS.png)

![snorm](assets/snorm_KA-NoS-Vehicle-NoS.png)

* ### KA-Surgery vs. Vehicle-Surgery

![norm](assets/norm_KA-S-Vehicle-S.png)

![snorm](assets/snorm_KA-S-Vehicle-S.png)

* ### Vehicle-NoSurgery vs. Vehicle-Surgery

![norm](assets/norm_Vehicle-NoS-Vehicle-S.png)

![snorm](assets/snorm_Vehicle-NoS-Vehicle-S.png)

## Fold Change

The following tables present the fold change information about the significant proteins (p < 0.01). Up or down regulation is addressed with `green` and `red` for up and down regulated expression level in the `color` columns.

### Fold change stats
#### KA-Surgery vs. KA-NoSurgery

* P < 0.01

 | Treatment group | Down regulated | Up-regulated | Total significant | % significant of all proteins identified |
 |:---|:---|:---|:---|:---|
 |KA-Surgery vs. KA-NoSurgery| 47 | 35 | 82 | 5.4% |
 |KA-NoSurgery vs. Vehicle-NoSurgery| 16  | 11 | 27 | 1.8% |
 |KA-Surgery vs. Vehicle-Surgery| 32 | 23 | 55 | 3.6% |
 |Vehicle-Surgery vs Vehicle-NoSurgery | 59 | 44 | 103 | 6.8%|


 * P < 0.05

 | Treatment group | Down regulated | Up-regulated | Total significant | % significant of all proteins identified | 
 |:---|:---|:---|:---|:---|
 |KA-Surgery vs KA-NoSurgery| 156 | 120 | 276 | 18%|
 |KA-NoSurgery vs. Vehicle-NoSurgery| 59 | 51 | 110| 7.3% |
 |KA-Surgery vs. Vehicle-Surgery| 113 | 80 | 193 | 12.8% |
 |Vehicle-Surgery vs Vehicle-NoSurgery | 170 | 103 | 273 | 18.1% |


Fold change is estimated based on the assumption that `KA-NoSurgery` condition is the control. The table is also accessible from [here](FoldChange/KA_NoSurgery.vs.Ka_Surgery.md).

![KA-Surgery-KA-NoSurgery](assets/FC-KA-noSurgery-KA-Surgery.png)
![KA-Surgery-KA-NoSurgery](assets/FC-KA-noSurgery-KA-Surgery.2.png)

* ### KA-NoSurgery vs. Vehicle-NoSurgery

Fold change is estimated based on the assumption that `KA-NoSurgery` condition is the control. The table is also accessible from [here](FoldChange/KA_NoSurgery.vs.Vehicle_NoSurgery.md).

![KA-NoSurgery-Vehicle-NoSurgery](assets/KA-NoSurgery-Vehicle-NoSurgery.png)

* ### KA-Surgery vs. Vehicle-Surgery

Fold change is estimated based on the assumption that `KA-Surgery` condition is the control. The table is also accessible from [here](FoldChange/KA_Surgery.vs.Vehicle_Surgery.md).

![KA-Surgery-Vehicle-Surgery](assets/KA-Surgery-Vehicle-Surgery.png)
![KA-Surgery-Vehicle-Surgery](assets/KA-Surgery-Vehicle-Surgery.2.png)

* ### Vehicle-Surgery vs. Vehicle-NoSurgery

Fold change is estimated based on the assumption that `Vehicle-Surgery` condition is the control. The table is also accessible from [here](FoldChange/Vehicle_NoSurgery.vs.Vehicle_Surgery.md).

![Vehicle-NoSurgery-Vehicle-Surgery](assets/Vehicle-nosergery.vs.surgery.png)
![Vehicle-NoSurgery-Vehicle-Surgery](assets/Vehicle-nosergery.vs.surgery.2.png)
![Vehicle-NoSurgery-Vehicle-Surgery](assets/Vehicle-nosergery.vs.surgery.3.png)


## Heat Map

Heat map is generated for significant proteins (P < 0.05). No clustering have been performed among samples.

* ###  KA-NoSurgery vs. KA-Surgery

![Heatmap](assets/heatmap-KA-NoSurgery-KA-Surgery.png)

* ### KA-NoSurgery vs. Vehicle-NoSurgery

![Heatmap](assets/heatmap-KA_NoSurgery-Vehicle-NoSurgery.png)

* ### KA-Surgery vs. Vehicle-Surgery

![Heatmap](assets/heatmap-KA-Surgery-Vehicle-Surgery.png)

* ### Vehicle-Surgery vs. Vehicle-NoSurgery

![Heatmap](assets/heatmap-Vehicle-Surgery-Vehicle-NoSurgery.png)


## Volcano Plot
In the following volcano plots, statistical significance is plotted agains the fold change. Proteins that are both significant (p < 0.05, -Log10 (p) > 2) and their expression level has changed more than 2 folds ( log2(fc) > 2 for upper expressed and log2(fc) < 2 for lower expressed proteins ) are shown in pink.

* ###  KA-NoSurgery vs. KA-Surgery

![volcano](assets/volcano_KA-NoS-KA-S.png)

* ### KA-NoSurgery vs. Vehicle-NoSurgery

![volcano](assets/volcano_KA-NoS-Vehicle-NoS.png)

* ### KA-Surgery vs. Vehicle-Surgery

![volcano](assets/volcano_KA-S-Vehicle-S.png)

* ### Vehicle-Surgery vs. Vehicle-NoSurgery

![volcano](assets/volcano_Vehicle-NoS-Vehicle-S.png)


## Kegg-Pathways

### KA-Surgery vs. Vehicle-Surgery

The first few rows of the pathways table look like this:

|General pathway| Detailed pathway|
|:--|:--|
|mmu03010 Ribosome - Mus musculus (mouse) (8)|mmu:19988 Rpl6; ribosomal protein L6|
|[  ](https://www.genome.jp/dbget-bin/www_bget?mmu)|mmu:20102 Rps4x; ribosomal protein S4, X-linked|
|[  ](https://www.genome.jp/dbget-bin/www_bget?mmu)|mmu:26451 Rpl27a; ribosomal protein L27A|

Complete table can be found [here](Pathways/KA-Surgery.vs.Vehicle-Surgery.md)

### Vehicle-Surgery vs. vehicle-NoSurgery

The first few rows of the pathways table look like this:

|Pathways | Detailed pathways|
|:--|:--|
| mmu01100 Metabolic pathways - Mus musculus (mouse) (14)|mmu:110078 Pygb; brain glycogen phosphorylase|
|      |mmu:11758 Prdx6; peroxiredoxin 6|
|      |mmu:12857 Cox4i1; cytochrome c oxidase subunit 4I1|
|      |mmu:14085 Fah; fumarylacetoacetate hydrolase|
|      |mmu:14651 Hagh; hydroxyacyl glutathione hydrolase|
|      |mmu:14866 Gstm5; glutathione S-transferase, mu 5|
|      |mmu:17161 Maoa; monoamine oxidase A|

Compleate table can be found [here](Pathways/Vehicle-Surgery.vs.Vehicle-NoSurgery.md)


### KA-NoSurgery vs. Vehicle-NoSurgery

The first few rows of the pathways table look like this:

|Pathways| detailed pathways|
|:--|:--|
|mmu01100 Metabolic pathways - Mus musculus (mouse) (7)|mmu:110821 Pcca; propionyl-Coenzyme A carboxylase, alpha polypeptide|
|[  ](https://www.genome.jp/dbget-bin/www_bget?mmu)|mmu:14645 Glul; glutamate-ammonia ligase (glutamine synthetase)|
|[  ](https://www.genome.jp/dbget-bin/www_bget?mmu)|mmu:14866 Gstm5; glutathione S-transferase, mu 5|
|[  ](https://www.genome.jp/dbget-bin/www_bget?mmu)|mmu:228550 Itpka; inositol 1,4,5-trisphosphate 3-kinase A|
|[  ](https://www.genome.jp/dbget-bin/www_bget?mmu)|mmu:56421 Pfkp; phosphofructokinase, platelet|
|[  ](https://www.genome.jp/dbget-bin/www_bget?mmu)|mmu:67003 Uqcrc2; ubiquinol cytochrome c reductase core protein 2|
|[  ](https://www.genome.jp/dbget-bin/www_bget?mmu)|mmu:67130 Ndufa6; NADH:ubiquinone oxidoreductase subunit A6|

Complete table can be found [here](Pathways/KA-NoSurgery.vs.Vehicle-NoSurgery.md)


### KA-Surgery vs. KA-NoSurgery

The first few rows of the pathways table look like this:

|General pathway| Detailed pathway|
|:--|:--|
|mmu03010 Ribosome - Mus musculus (mouse) (8)|mmu:19988 Rpl6; ribosomal protein L6|
|[  ](https://www.genome.jp/dbget-bin/www_bget?mmu)|mmu:20102 Rps4x; ribosomal protein S4, X-linked|
|[  ](https://www.genome.jp/dbget-bin/www_bget?mmu)|mmu:26451 Rpl27a; ribosomal protein L27A|
|[  ](https://www.genome.jp/dbget-bin/www_bget?mmu)|mmu:26961 Rpl8; ribosomal protein L8|
|[  ](https://www.genome.jp/dbget-bin/www_bget?mmu)|mmu:66489 Rpl35; ribosomal protein L35|

Complete table can be found [here](Pathways/KA-NoSurgery.vs.KA-Surgery.md)


## ANOVA

For multi-group analysis, one-way Analysis of Variance (ANOVA) has been performed.  As ANOVA only tells whether the overall comparison is significant or not and it does not give any infromation on which groups or features are different. Fisher’s least significant difference method (Fisher’s LSD) was used to identify which two levels are different.

### Heatmap

![Heatmap](assets/heatmap-anova.png)

### Abundance distribution

![Abundances](assets/abundances-anova.png)
