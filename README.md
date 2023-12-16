---
editor_options: 
  markdown: 
    wrap: 72
---

# Final-Project

# United States Drug-Related Deaths Analysis

**Team members**: Zehui Li, Lezhi Cao, Mujin Li, Xinwen Zhang

## Literature Review

In our project, we integrate the findings of several key studies to
understand drug-related deaths. Merrall et al. (2010) and Gaston et al.
(2009) both highlight the acute risks and intervention opportunities
surrounding drug use. Juntti-Patinen & Neuvonen (2002) and Püschel
(1993) provide insights into hospital-related fatalities and the danger
of heroin overdoses, respectively. Lastly, Dai et al. (2019) underline
the emerging threat of fentanyl. These studies collectively inform our
approach, emphasizing the need for a multifaceted strategy to address
the complex drug crisis landscape.

### Project Instructions

#### Setting Up the Environment

1.  Install R and RStudio.
2.  Use `install.packages()` to install required libraries listed at the
    beginning of the script.

#### Data Acquisition

1.  Download datasets from the provided links or use APIs to retrieve
    the latest data.
2.  Store the data in a directory named `/data`.

#### Running the Analysis

1.  Execute the data preprocessing scripts to clean and merge datasets.
2.  Run the geospatial analysis code to visualize drug-related death
    trends.
3.  Perform machine learning analysis using the provided scripts to
    build and evaluate models.

#### Replicating the Study

1.  To replicate the findings, follow the order of the scripts from data
    preprocessing to machine learning modeling.
2.  For predictive modeling, ensure cross-validation and model tuning
    steps are correctly executed.

#### Contributing

-   If you wish to contribute to this project, please fork the
    repository and submit a pull request.

#### Project Overview

This study provides a comprehensive analysis of drug-related deaths in
the United States, integrating socioeconomic data, geographic
information, and advanced machine learning techniques to understand and
predict mortality trends.

#### Data Collection and Preprocessing

Datasets encompassing poverty rates, unemployment figures, GDP,
population, area, income levels, and high school graduation rates were
meticulously cleaned and merged. Additional data were retrieved using
Census Bureau APIs, ensuring a rich dataset for analysis.

#### Geospatial Analysis

A detailed visualization of drug death data was conducted to identify
geographic patterns and state-specific trends in drug-related mortality
from 2015 to 2021.

#### Machine Learning Modeling

We employed unsupervised learning (K-means clustering) to detect
inherent groupings within the data, and supervised learning (Ridge
Regression and Random Forest) to predict future trends. Model selection
was guided by cross-validation and RMSE performance metrics.

#### Key Findings and Discussion

The project highlights the critical socioeconomic predictors of drug
death rates and underscores the regional disparities in these trends.
The predictive models provide actionable insights for policymakers.
While robust, our models are limited by data availability and changing
societal trends, marking the path for future research.

#### Usage Instructions

The repository contains scripts and datasets for replication and
application to similar datasets. Users can follow the scripts for data
preprocessing, geospatial visualization, and machine learning analysis.

## Part 1. Data Description and Clean

In this project, we compiled data from various sources spanning the
years 2015 to 2022, encompassing a wide array of indicators for each
state. These indicators include poverty rates, population figures,
median income levels, high school graduation numbers, land area, water
area, and unemployment rates. To procure this diverse dataset, we
employed a combination of methods, including direct web downloads and
API access.

Given the heterogeneous formats of data from different sources, our data
cleaning process was crucial. We harnessed tools like `pivot_longer` and
`columnnames` to standardize the data format, making it amenable for
merging and subsequent cleaning operations.

After an initial examination of the data, we systematically addressed
missing values by either removing variables with significant data gaps
or imputing missing values with zeros. This rigorous data preparation
phase ensured the integrity and consistency of our dataset, setting the
stage for robust analysis and insights.

Reference: [Overdose Death: CDC/National Center for Health
Statistics](https://www.cdc.gov/nchs/pressroom/sosmap/drug_poisoning_mortality/drug_poisoning.htm)
[Poverty: United States Census
Bureau](https://www.census.gov/library/publications/2023/demo/p60-280.html)
[Area: World Population
Review](https://worldpopulationreview.com/state-rankings/states-by-area)
[Population: United States Census
Bureau](https://www.census.gov/popclock/) [GDP: United States Census
Bureau](https://data.census.gov/) [High Scool Graduation Number : United
States Census Bureau](https://data.census.gov/) [Unemployment Rate :
United States Census Bureau](https://data.census.gov/)

## Part 2. Drug Death Analysis

### Analysis Strategy:

Data is filtered to focus on 2015-2021, capturing recent trends.
Cumulative and per capita drug deaths by state are calculated to provide
both absolute and relative perspectives. Time series visualization
identifies key periods of change.

#### Drug Death Rate Analysis

Cumulative Drug Deaths (2015-2021): The analysis highlights that states
like California and Florida have the highest cumulative drug deaths.
This suggests regional variances possibly influenced by factors like
population density, drug availability, or state-specific policies.

Per Capita Drug Deaths: West Virginia has the highest per capita drug
death rate, indicating a disproportionate impact relative to its
population size. This emphasizes the need for targeted interventions in
such high-impact areas.

Temporal Trends: The time series analysis reveals major fluctuations in
drug deaths during 2017-2019. This period might correlate with specific
health crises or policy changes, warranting further investigation.

These findings provide crucial insights for understanding and addressing
the drug death crisis, emphasizing the need for region-specific
strategies and responsive policy-making.

## Visual Analysis:

![disparities in drug-related deaths across the U.S.](URL_of_the_image)

The first map displays significant disparities in drug-related deaths
across the U.S. from 2015-2021. The highest cumulative deaths are
evident in California and Florida, while West Virginia shows a notable
intensity in death per capita, indicating that despite its smaller
population, the impact of drug fatalities is substantial.

![annual drug deaths](URL_of_the_image)

The second chart depicts annual drug deaths, with a highlighted region
between 2017 and 2019. This period shows a marked increase in drug
fatalities, particularly in states like California, Florida, and New
York. The highlighted surge could suggest a worsening of the drug crisis
or changes in reporting or drug policy impacts during those years.

Together, these visualizations underscore the critical nature of the
drug crisis, varying significantly by state and over time, and highlight
the importance of context-specific analysis in public health
interventions.

## Drug Death Distribution and Prediction Analysis

#### Yearly Drug Death Distribution Visualization

This section visualizes the national distribution of drug deaths from
2015 to 2021, highlighting changes in state drug death counts over the
years. The visualization uses density ridges to represent the
distribution and density of drug deaths, capturing the variance and
trends within the data.

#### Predictive Models and Geospatial Visualization

Two predictive models, Ridge Regression and Random Forest, were used to
forecast state-level drug death rates. The subsequent geospatial
visualizations display the predicted rates across the U.S., providing a
visual representation of the models' outputs.

#### Visual Analysis

![Aggregate National Distribution of State Drug Death in the US: 2015 -
2021](URL_of_the_image)

Analyzing the first image, a ridge plot showcases the distribution of
drug deaths across states from 2015 to 2021. The peaks and valleys in
the plot indicate the density and distribution of deaths each year, with
color gradations representing quartiles. The 2021 layer shows a stark
contrast between the highest and lowest quartiles, indicating a growing
disparity in drug deaths across states.

![Predicted Drug Death Rates for Different States in the
US](URL_of_the_image)

The second image comprises two maps predicting drug death rates using
Ridge Regression and Random Forest models. Both maps display variations
in death rates across states, with darker colors signifying higher
predicted rates. The models seem to forecast a higher concentration of
drug-related fatalities in specific regions, which could guide targeted
public health responses.

These analyses combine statistical and machine learning methods with
geospatial data to provide a comprehensive view of the drug death
landscape in the U.S., highlighting areas of concern and aiding in
policy formulation.

## Machine Learning

### Model Specifications

#### K-means Clustering:

Used to identify hidden patterns and group states with similar drug
death characteristics. Optimal clusters were determined by minimizing
WSS and maximizing silhouette scores.

**Ridge Regression:** Chosen for its ability to manage multicollinearity
among predictors. Model complexity was controlled through
cross-validated penalty tuning.

**Random Forest:** Selected for its robustness to outliers and model
flexibility. The algorithm's hyperparameters, such as the number of
trees and minimum node size, were optimized through cross-validation.

#### Model Performance Comments

Ridge Regression provided a quantifiable measure of feature importance,
allowing for the identification of the most influential predictors of
drug death rates.

Random Forest's ensemble approach was key to capturing complex,
non-linear relationships, potentially leading to more nuanced
predictions.

#### Outcome:

The models' predictions for 2022 death rates can inform regional health
strategies. For instance, areas predicted to have higher death rates
might need more intensive intervention programs. Visual comparisons
between models offer insights into areas of agreement and divergence,
highlighting the inherent uncertainty in predictions and the need for
robust policy frameworks that can adapt to such uncertainties.

#### Visual Analysis

![K-Means with K = 4 and PCA](URL_of_the_image)

**K-Means Clustering:** The scatter plot indicates four distinct
clusters, suggesting that the dataset can be divided into four groups
based on the features considered. One cluster, in particular, appears to
be an outlier, significantly distanced from the others along PC1.

![mean WSS over 5 folds](URL_of_the_image)

**WSS Plot:** The elbow plot for WSS shows a sharp decline as the number
of clusters increases from 1 to 4, after which the decline in WSS slows
down. This suggests that four clusters provide a reasonable balance
between within-cluster variance and the number of clusters.

![Number of clusters](URL_of_the_image)

**Silhouette Plot:** The silhouette plot supports the choice of four
clusters, as the mean silhouette score starts to plateau after four
clusters, indicating that additional clusters do not provide a
significant structure improvement.

![Importance Score(Ridge with Penalty)](URL_of_the_image)

**Ridge Regression:** The bar chart shows that "death_numbers"" and
"population"" have the highest importance scores in the Ridge Regression
model, implying they are strong predictors of the outcome variable.

![RMSE Across Ridge Regression Resamples](URL_of_the_image)

**RMSE Across Ridge Regression Resamples:** The multi-line plot displays
RMSE across different penalties for Ridge Regression. Lower penalties
seem to yield lower RMSE, suggesting better model performance.

![RMSE Across Random Forest Resamples](URL_of_the_image)

**RMSE Across Random Forest Resamples:** The plot shows RMSE for
different "mtry"" values in Random Forest, with some volatility across
the folds. The optimal "mtry"" seems to be around the middle range,
neither too low nor too high.

**Data Analysis:** The chosen tools, including K-means clustering, Ridge
Regression, and Random Forest, align with the complexity of drug-related
death data. K-means helps to identify inherent groupings in the data
which can inform targeted interventions. Ridge Regression manages
multicollinearity and overfitting, critical in datasets with many
correlated predictors. Random Forest captures non-linear patterns and
interactions between predictors. Model evaluation, conducted through
cross-validation and performance metrics like RMSE, ensures robustness
and reliability of the predictions.

**Discussion of Results:** The clustering revealed distinct groups in
the data, which could represent varying levels of drug death risk across
regions. The Ridge Regression importance score highlighted key factors,
with 'death_numbers' and 'population' being the most significant
predictors. The RMSE plots indicate that both Ridge and Random Forest
models provide reasonable predictions, but they might perform
differently on unseen data. Limitations include potential biases in the
data and the static nature of models against evolving trends. Future
research should focus on incorporating more dynamic data and exploring
causal inference models.

## Conclusion

Our project's findings paint a clear picture: drug-related deaths in the
US are not just numbers but reflect deeper societal issues. Through data
analysis, we've seen how factors like education, income, and location
are intertwined with these tragedies. Our models offer a way to predict
where the problem might hit hardest next. They're tools for those in
charge to take action, to focus on places and people at greatest risk.
It's a call to look beyond the data, to real lives, and to use this
knowledge to save them. Looking ahead, we hope our work inspires more
up-to-date research and real-time solutions.

## limitation

The project's main limitation lies in its reliance on historical and
static data, which may not capture real-time changes or the latest
trends in drug-related deaths. Additionally, socioeconomic and health
data can be subject to reporting biases and inaccuracies. There's also a
risk of oversimplifying complex social issues when using machine
learning models, which might not fully account for nuanced factors
influencing drug mortality rates. These limitations highlight the need
for continuous data updates and more sophisticated models that can adapt
to evolving societal dynamics.

## References

1.  C. Merrall, E. L., Kariminia, A., Binswanger, I. A., Hobbs, M. S.,
    Farrell, M., Marsden, J., Hutchinson, S. J., & Bird, S. M. (2010).
    Meta-analysis of drug-related deaths soon after release from prison.
    Addiction, 105(9), 1545-1554.
    <https://doi.org/10.1111/j.1360-0443.2010.02990.x>
2.  Juntti-Patinen, .L., Neuvonen, .P. Drug-related deaths in a
    university central hospital. Eur J Clin Pharmacol 58, 479--482
    (2002). <https://doi.org/10.1007/s00228-002-0501-2>
3.  Püschel, K. (1993). Drug-related death --- An update. Forensic
    Science International, 62(1-2), 121-128.
    [https://doi.org/10.1016/0379-0738(93)90056-G](https://doi.org/10.1016/0379-0738(93)90056-G){.uri}
4.  Gaston, R.L., Best, D., Manning, V. et al. Can we prevent drug
    related deaths by training opioid users to recognise and manage
    overdoses?. Harm Reduct J 6, 26 (2009).
    <https://doi.org/10.1186/1477-7517-6-26>
5.  Dai, Z., Abate, M. A., Smith, G. S., Kraner, J. C., & Mock, A. R.
    (2019). Fentanyl and fentanyl-analog involvement in drug-related
    deaths. Drug and Alcohol Dependence, 196, 1-8.
    <https://doi.org/10.1016/j.drugalcdep.2018.12.004>
