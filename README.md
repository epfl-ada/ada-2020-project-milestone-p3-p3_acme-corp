## Title 
Civil wars for dummies

## Abstract
History shows different reasons for war including religion, ethnic injustice, and economic hardship. We wonder whether these different types are visible in the data and whether clustering wars will lead to different profile definitions. There has been a huge effort in interpreting models like random forest which are considered as black box. We use rule extraction methods to derive simplified rules for when civil war happens. The paper considers  snapshot records of countries - without context. The growth and diminishment of resources and productivity of a country over the years can be a sign of upcoming troubles. We want to know how war impacts trade between countries. Is war bad for business or it is an opportunity for making profit? After studying the impact of war on trade, we study whether merchants increase/decrease their trade with countries on the verge of war.


## Research Questions
**Time**:
 - The paper considers snapshot views of countries for each year. Does adding more information about the past of a country help to make better predictions ? 
 - The paper fixes the start of a civil war to one specific moment in time, while tension in countries is built over time. Does expanding the period when the civil war starts to multiple years improve the prediction of future civil wars?
**Clustering wars**:
 - Do we have different types of civil wars? We guess that there are different types of civil wars based on the primary reason for war which can be economic, religious, social, or ethnical injustice, etc. Does the data suggest that there are different clusters of civil wars?
 - If we have different categories of civil wars, how does the underlying reasons of civil war onset differ between them ?
**Trade**:
 - Is war bad for business?  We study whether war has a negative impact on trade. 
 - Are merchants better than politicians in detecting civil wars? Civil wars are bad for profit. Do merchants predict civil wars and reduce their trade quantity ahead of the war? (only if war is bad for trades)
**Improve interpretability**:
 - Is it possible to obtain a set of simple observations or rules leading to a good estimate of whether a civil war will appear?

## Proposed dataset
- Bilateral trades: We use this dataset to detect the decline of trade in countries. (https://correlatesofwar.org/data-sets/bilateral-trade)[Barbieri, Katherine, Omar M. G. Keshk, and Brian Pollins. 2009. “TRADING DATA: Evaluating our Assumptions and Coding Rules.” Conflict Management and Peace Science. 26(5): 471-491.]
 - War since 1800: We use this dataset to add information about countries at war to analyze the impact of war on neighbouring countries. (https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/ZN1WLF&version=1.0)[Mafrica, Chelsea, 2016, "Place, Population, Precipitation, War since 1800", https://doi.org/10.7910/DVN/ZN1WLF, Harvard Dataverse, V1]   

## Methods
**Data collection**: Historical data will be obtained by augmenting records with computing relative change over year in numerical stats. We use “war since 1800” to augment data with inter-country wars. We clean the “bilateral trade” dataset without directly joining it with the original data as it considers trade flows between pairs of countries.  

**Time series analysis**: We train a classification model with aggregated data for multiple years combined and compare it to the original model based on an input of a single year, to understand the difference in predictive power when using more data from the years ahead.

**Feature importance analysis**: We apply the guidelines from Understanding Random Forests by Gilles Louppe (2014). The method will make use of very low-depth random forests trained in a specific manner.

**Prediction rule analysis**: We apply methods from the field of rule extraction like skope-rules to obtain an easy to interpret model with predictive power close to the original random forest.

**Clustering and category analysis**: The different types of civil wars will be observed by applying a dimensionality reduction technique. The intended algorithm is T-SNE since it is well known for its ability to work with high dimensional and non-linear datasets. Any easy to interpret classification algorithm could be used to derive rules for understanding the clusters. We plan to use low-depth decision trees and logistic regression.

**Trade analysis**: We mark the different stages of war in the dataset as stable, pre-war (~2-3 years before the war), war, and post war (~2-3 year after the war). We use statistical analysis to compare how the trade flows change during these periods.



## Proposed timeline
Week 1:
 -[ ] Data cleaning
   -[ ] Adding historical data
   -[ ] Merging with war dataset
   -[ ] Augmenting the dataset with stable pre-war, war, and post-war signals
   -[ ] Starting with the trade dataset

 -[ ] Performing the analysis tasks and getting preliminary result
   -[ ] Assessing properly the features’ importance using random forest
   -[ ] Dimensionality reduction from the high-dimensional space and clustering. Interpretation of those clusters.
   -[ ] Classification on the clusters
 - [ ]Analyse how trade changes with war
Week 2:
 - [ ] Building the site
 - [ ] Writing the story
 - [ ] Adding interactive plots
Week 3:
 - [ ] Refining the story
 - [ ] Filling gaps in the story with more analysis

## Organization within the team
 - Interpretability analysis: Maximilian
 - Clustering analysis: Baptiste
 - Feature importance: Baptiste
 - Trading analysis: Kasra
 - Timing analysis: Kasra and Maximilian
 - Building the site and writing the story will be a collaboration between all members.
