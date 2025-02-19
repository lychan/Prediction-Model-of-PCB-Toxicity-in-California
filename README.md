# Using Machine Learning to Predict Locations with High PCB Toxicity Levels in Fish

## Project Intro/Objective

**Problem Statement**: How can we use machine learning to determine areas in California where PCBs has accumulated in aquatic organisms? 

**Solution**: Using a prediction model to build an interactive map showing which area and in which species shows the most occurrences of samples with PCBs level over 
threshold

**Project Goal**: Explore how can we leverage machine learning to address complex ecological challenges, mitigate climate change, restore ecosystems, and engage a greater audience 

**Project Ojective** Creating a proof of concept for the solution proposed


## Key Words:

**What is PCB?**

PCB refers a group of man-made chemicals called polychlorinated biphenyls. There were mostly widely used in coolants and lubricants in transformers, capacitors, and other electrical equipment, until they were banned in the late 1970s. They do not break down easily and can remain in environment for decades.

Adverse effects on humans include liver damage, cancer, neurobehavioral changes, and developmental health issues. According to EPA guidelines, the maximum allowable level of polychlorinated biphenyls (PCBs) is 75 nanograms per gram of wet weight (ww) in any given substance.

**What is Biomagnification?**

Biomagnification is the process by which the concentration of toxic substances increases exponentially as they move up the trophic levels in marine food chains.


## Potential impacts:
* Help researchers and cleanup groups to understand where polluted hotspots are- Department of Toxic Substances Control (DTSC) & U.S. Environmental Protection Agency
  
* Help recreational fisher-people to know where is not safe for fishing, particularly which species in a given location

## Installation and Setup

Clone this repo (for help see this [tutorial](https://help.github.com/articles/cloning-a-repository/))

### Codes and Resources Used
Editor Used: VS Code, 
Python Version: Python 3.12.7
Python Packages Used

* General: Jupyter Notebook, Anachonda
* Data Manipulation: pandas, numpy
* Data Visualization: plotly, seaborn, matplotlib 
* Machine Learning: scikit-learn

## Data

### Source Data

Source raw data were downloaded from [here](https://data.ca.gov/dataset/surface-water-aquatic-organism-tissue-sample-results)

For this project, I used five years of tissue data in order to gain a more comprehensive pattern, pulling from 2020-2024. This data set provides results of tissue from organisms found in surface waters. The data are of tissue from individual organisms and of composite samples where tissue samples from multiple organisms are combined and then analyzed. Both the individual samples and the composite sample results may be given so for individual samples, there will be a row for the individual sample and a row for the composite where the number per composite is one. 

### Data Preprocessing



### Code structure

Dataframe needed to run the final modeling is [here](Repo folder containing data processing scripts/notebooks)


├── data
│   ├── data1.csv
│   ├── data2.csv
│   ├── cleanedData
│   │   ├── cleaneddata1.csv
|   |   └── cleaneddata2.csv
├── data_acquisition.py
├── data_preprocessing.ipynb
├── data_analysis.ipynb
├── data_modelling.ipynb
├── Img
│   ├── img1.png
│   ├── Headerheader.jpg
├── LICENSE
├── README.md
└── .gitignore

## Results and evaluation
Provide an overview of the results of your project, including any relevant metrics and graphs. Include explanations of any evaluation methodologies and how they were used to assess the quality of the model. You can also make it appealing by including any pictures of your analysis or visualizations.
   

## Future work
Outline potential future work that can be done to extend the project or improve its functionality. This will help others understand the scope of your project and identify areas where they can contribute.







  
#### Project Steps:

##### Sprint 1
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

##### Sprint 2
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


##### Sprint 3

Final Model Selection 


##### Sprint 4

App Deployment

## Getting Started

1. Clone this repo (for help see this [tutorial](https://help.github.com/articles/cloning-a-repository/))
2. Raw Data & temporary datasets for cleaning and EDA is kept here [Google Link](https://drive.google.com/drive/folders/1kPnh-0KWNwPPuPcm21qYIKYdAne6DzEr?usp=sharing)
3. Source raw data were downloaded from [here](https://data.ca.gov/dataset/surface-water-aquatic-organism-tissue-sample-results)   
4. Final Notebooks folder contains scripts need to run the project is [here (Repo folder containing data processing scripts/notebooks)]
5. Dataframe needed to run the final modeling is [here](Repo folder containing data processing scripts/notebooks)
6. Sprint Notebooks documenting reiterative process (for archiving process, do not use for modeling) is [here](Repo folder containing data processing scripts/notebooks)


## Featured Notebooks/Analysis/Deliverables
* [Notebook/Markdown/Slide Deck Title](link)
* [Notebook/Markdown/Slide DeckTitle](link)
* [Blog Post](link)








