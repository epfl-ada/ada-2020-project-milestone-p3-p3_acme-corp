# Civil wars for dummies

## Abstract
History shows different reasons for war including religion, ethnic injustice, and economic hardship. We wonder whether these different types are visible in the data and whether clustering wars will lead to different profile definitions. There has been a huge effort in interpreting models like random forest which are considered as black box. We use rule extraction methods to derive simplified rules for when civil war happens. The paper considers  snapshot records of countries - without context. The growth and diminishment of resources and productivity of a country over the years can be a sign of upcoming troubles. We want to know how war impacts trade between countries. Is war bad for business or it is an opportunity for making profit? After studying the impact of war on trade, we study whether merchants increase/decrease their trade with countries on the verge of war.


## Research Questions
**Time**:
 - The paper considers snapshot views of countries for each year. Does adding more information about the past of a country help to make better predictions ? 

 We added variables representing the change of original variables over year to study the impact of expanding data as a time sequence, but we did not observe any significant change in the classification

**Clustering wars**:
 - Do we have different types of civil wars? We guess that there are different types of civil wars based on the primary reason for war which can be economic, religious, social, or ethnical injustice, etc. Does the data suggest that there are different clusters of civil wars?
 - If we have different categories of civil wars, how does the underlying reasons of civil war onset differ between them ?

Due to medical emergency Baptiste had to leave the team in the last stage of the project and despite having preliminary results in clustering they are not present in the final version.

**Trade**:
 - Is war bad for business?  We study whether war has a negative impact on trade. 
 - Are merchants better than politicians in detecting civil wars? Civil wars are bad for profit. Do merchants predict civil wars and reduce their trade quantity ahead of the war? (only if war is bad for trades)

The trade data is very fickle and it varies a lot between year. Separating temporal effects from effect of war will be very challenging. Moreover, we found out that that the unfairness in war results in very different situation for the two sides of war as participating in war can range from sending 1000 troops to another country to chemical bombardment of cities. 

**Improve interpretability**:
 - Is it possible to obtain a set of simple observations or rules leading to a good estimate of whether a civil war will appear?

 We used skope-rule to enhance the interoperability of the model. We realized that the ROC curve is not suitable for civil war which is unbalanced. Surprisingly, rules achieve a better F1 than the more complex RF in the paper.

## Proposed dataset
- Bilateral trades: We use this dataset to detect the decline of trade in countries. [Barbieri, Katherine, Omar M. G. Keshk, and Brian Pollins. 2009. “TRADING DATA: Evaluating our Assumptions and Coding Rules.” Conflict Management and Peace Science. 26(5): 471-491.](https://correlatesofwar.org/data-sets/bilateral-trade)
 - War since 1800: We use this dataset to add information about countries at war to analyze the impact of war on neighbouring countries. [Mafrica, Chelsea, 2016, "Place, Population, Precipitation, War since 1800", https://doi.org/10.7910/DVN/ZN1WLF, Harvard Dataverse, V1](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/ZN1WLF&version=1.0)   

## Methods
**Data collection**: Historical data will be obtained by augmenting records with computing relative change over year in numerical stats. We use “war since 1800” to augment data with inter-country wars. We clean the “bilateral trade” dataset without directly joining it with the original data as it considers trade flows between pairs of countries.  

**Time series analysis**: We train a classification model with aggregated data for multiple years combined and compare it to the original model based on an input of a single year, to understand the difference in predictive power when using more data from the years ahead.

**Feature importance analysis**: We apply the guidelines from Understanding Random Forests by Gilles Louppe (2014). The method will make use of very low-depth random forests trained in a specific manner.

**Prediction rule analysis**: We apply methods from the field of rule extraction like skope-rules to obtain an easy to interpret model with predictive power close to the original random forest.

**Clustering and category analysis**: The different types of civil wars will be observed by applying a dimensionality reduction technique. The intended algorithm is T-SNE since it is well known for its ability to work with high dimensional and non-linear datasets. Any easy to interpret classification algorithm could be used to derive rules for understanding the clusters. We plan to use low-depth decision trees and logistic regression.

**Trade analysis**: We mark the different stages of war in the dataset as stable, pre-war (~2-3 years before the war), war, and post war (~2-3 year after the war). We use statistical analysis to compare how the trade flows change during these periods.



## Proposed timeline
Week 1:
 - [x] Data cleaning
   - [x] Adding historical data
   - [x] Merging with war dataset
   - [x] Augmenting the dataset with stable pre-war, war, and post-war signals
   - [x] Starting with the trade dataset
 - [-] Performing the analysis tasks and getting preliminary result
   - [-] Assessing properly the features’ importance using random forest
   - [-] Dimensionality reduction from the high-dimensional space and clustering. Interpretation of those clusters.
   - [-] Classification on the clusters
 - [x] Analyse how trade changes with war

Week 2:
 - [x] Building the site
 - [x] Writing the story
 - [x] Adding interactive plots

Week 3:
 - [x] Refining the story
 - [x] Filling gaps in the story with more analysis

## Organization within the team
 - Interpretability analysis: Maximilian
 - Trading analysis: Kasra
 - Timing and augmenting data: Kasra 
 - ~Clustering analysis: Baptiste~
 

Due to medical emergency Baptiste had to leave the team in the last stage of the project and despite having preliminary results in clustering they are not present in the final version.