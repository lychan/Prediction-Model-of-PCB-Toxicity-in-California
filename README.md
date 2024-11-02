# Capstone-Project
Brainstation Capstone Project

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










Dataset: https://drive.google.com/drive/u/0/folders/1Got0Z6ZovulmD01pmx4G-LxNgNWBOMHm
