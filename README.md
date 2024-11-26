# Prediction of chemical levels found in aquatic organism tissues in California
This project is a part of the Data Science Capstone Project for BrainStation


## Project Intro/Objective
The purpose of this project is to be able to pinpoint which species in which location is most likely to have an elevated amount of PCBs in its tissues .

#### Potential impacts:
* Help researchers and cleanup groups to understand where polluted hotspots are
* Help recreational fisher-people to know where is not safe for fishing, particularly which species in a given location


### Methods Used
* Linear Regression
* Logistic Regression
* Machine Learning
* Data Visualization
  

### Technologies
* Python
* Pandas, jupyter
* Sklearn
* MatPlotLib, Seaborn, Plotly
   

### Project Description
#### Sprint 1
For Sprint 1 of the project, I collected and took a preliminary look into the data. 
Originally, I had wanted to look at the relationship between water pd levels and temperature and see how that affects the chemical levels in the species, but I could not find relevant data for it.

After concatenating 5 years of tissue data, I have found that it could be interesting to look at the relationships between the species, chemicals, any correlations between the chemicals themselves, and the location.

There is 216,797 rows of data, so I took a random 20% sample to look at

When looking at the null values, I found that one of the core columns for this analysis, "Result", has 42% nulls. I had to take a deeper dive to understand what they name
In addition, I had found over 7000 duplicate rows, which is 16% of my dataset. I hestitated to drop them as they could contain valuable results.

Some of the results columns have measurements in different units stored, I filtered out those rows, converted the values, and overwrote the dataset
I also dropped columns that does not pertain important information to my analysis, as well as columns that contains duplicate values.
One of my main challenges is the amount of unique values in the columns that I want to analysis. Currenly, more research is needed to do meaningful groupings, which would be part of my next steps.

Another of big challenge is pivoting the analytes columns so that each analyte would become its own column header, with it's corresponding result per tissue sample underneath. Initially this method worked when I dropped  values.
However, after receiving feedbacks from the presentations today, I decided to keep the duplicate values for now, but it is causing issues with the pivoting and merging. 
Without being able to separate out the analyte into multiple columns, I cannot do any meaningful EDA to determine the treatment of the duplicate values. Figuring out a solution to this is imperlative as my next step.

#### Sprint 2
For Sprint 2, I gropued the 95 species to 13 species groups based on saltwater vs freshwater environments, and trophic levels
There is still 15% null and 37% duplicated values. I dropped the duplicated values
For the null values, for the mass/length measurement values, I used the median. For missing results for analyte levels, I pushed them to 0 since a 0 would me analyte not detected. 

Then I made baseline models with 2 linear and 2 logistic models
For both models, I used correlation heatmap & VIF to detect multicollinearity

For the linear model, I used the Ordinary least squares, backward selection regression
For model evaluation, I used null hypothesis P-values to evaluate level of prediction, and R2 value to measure goodness of fit. Plotting residuals, Shapiro-Wilk test, and checking homoscedasticity.

For the logistics model, I used L1 Regularization. Didn't get to do model evaluations

Next steps:

Do train-test split on logistic model to check for potential overfitting, and explore scalers, calculate precision & recall values, ROC & AUC Scores
If target variable datapoint is too low, consider adding in more years into dataset
Explore Decision Tree and/or Random Forest models
Restructure data to combine latitude & longitude as a location point. Right now longitude is being dropped due to strong collinearity to latitude. 




## Needs of this project

- frontend developers
- data exploration/descriptive statistics
- data processing/cleaning
- statistical modeling
- writeup/reporting
- etc. (be as specific as possible)

## Getting Started

1. Clone this repo (for help see this [tutorial](https://help.github.com/articles/cloning-a-repository/)).
2. Raw Data is being kept [here](Repo folder containing raw data) within this repo.

    *If using offline data mention that and how they may obtain the data from the froup)*
    
3. Data processing/transformation scripts are being kept [here](Repo folder containing data processing scripts/notebooks)
4. etc...

*If your project is well underway and setup is fairly complicated (ie. requires installation of many packages) create another "setup.md" file and link to it here*  

5. Follow setup [instructions](Link to file)

## Featured Notebooks/Analysis/Deliverables
* [Notebook/Markdown/Slide Deck Title](link)
* [Notebook/Markdown/Slide DeckTitle](link)
* [Blog Post](link)


## Contributing DSWG Members

**Team Leads (Contacts) : [Full Name](https://github.com/[github handle])(@slackHandle)**

#### Other Members:

|Name     |  Slack Handle   | 
|---------|-----------------|
|[Full Name](https://github.com/[github handle])| @johnDoe        |
|[Full Name](https://github.com/[github handle]) |     @janeDoe    |

## Contact
* If you haven't joined the SF Brigade Slack, [you can do that here](http://c4sf.me/slack).  
* Our slack channel is `#datasci-projectname`
* Feel free to contact team leads with any questions or if you are interested in contributing!








Dataset: https://drive.google.com/drive/u/0/folders/1Got0Z6ZovulmD01pmx4G-LxNgNWBOMHm
