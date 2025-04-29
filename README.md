# Phase 1 Project - Analysis of Aircraft Risk
## Project Goal
This project aims to extract meaningful insights about aircraft risk and make reliable recommendations for purchase and product diversification to the head of the new aviation division
in an expanding company.

# Business Understanding
Expanding a company into new industries requires market research and the strategic reallocation of resources. 
In this case, the client want to purchase and operate commercial and private airplanes to diversify their company's portfolio. 
Specifically, they want to identify the lowest risk aircraft for the company which means they must have a proven track record of safety and reliability. 
This metric is provable by a long history of few or no incidents and aerodynamic efficiency. Another factor to consider is whether the aircraft is reliable in varying weather conditions. 
In addition, their structural design must be professional and have advanced safety features.
The stakeholders are the businessmen looking to expand their company. 
They can use this project in sourcing safe and low risk aircraft with few to little incidents or negative impacts to human life.
A combination of these factors will produce an airworthy craft with low risk factors, enhanced profitability and revenue growth for the company. 
Moreover, catering to both commercial and private demographics ensures an increased market share by offering a broad range of products and services.
The output of this notebook will be valuable in reducing injuries caused by aircrafts.

## Data Source and Data Exploration
This project will analyse the [Kaggle Aviation Accident Database & Synopses dataset](https://www.kaggle.com/datasets/khsamaha/aviation-accident-database-synopses). The source contains 88889
rows of which 87951 contain unique values. Each entry describes an accident or incident report collected from 1962 about civil aviation accidents in the United States.
I used 11 columns from the original 30 which included variables such as 
- Injury Severity,
- Make
- Model
- Aircraft damage
- Number of Engines
- Engine type
- Total fatal injuries
- Total serious injuries
- Total minor injuries
- Total uninjured
- Weather condition
- Broad phase of flight

## Data Preparation
I utilized Python and Virtual Studio Code to load, prepare, analyze, and visualize the dataset.
Python versions 3.8.5, 3.11.7, and 3.13.7 are effective.
These are the packages i used in data analysis and visualization:

![importation](https://github.com/user-attachments/assets/2cec92e7-3021-4eee-b4f8-709983260308)

I created a clean dataset by dropping missing values using the following dataframe function:
```Python
df_clean = df.dropna(subset=['Injury.Severity','Make', 'Model','Aircraft.damage', 'Number.of.Engines', 'Engine.Type','Total.Fatal.Injuries',
       'Total.Serious.Injuries', 'Total.Minor.Injuries', 'Total.Uninjured',
       'Weather.Condition', 'Broad.phase.of.flight'])
```
I then dropped duplicated data and created a sample of 100 aircrafts since working with the entire dataset of 88889 was proving difficult to visualize:
```Python
unique_aircrafts = df_clean.drop_duplicates(subset = ['Combined'])
df_sample = unique_aircrafts.sample(n = 100, random_state= 42)
```
To facilitate risk calculation, I combined the Total fatal injuries, Total serious injuries, and Total minor injuries columns to create a 'Total Injuries' column which depicts the overall
injries sustained by each aircraft.
```Python
def calculate_total(row):
    return row['Total.Fatal.Injuries'] + row['Total.Serious.Injuries'] + row['Total.Minor.Injuries']

df_sample['Total Injuries'] = df.apply(calculate_total, axis=1)
```
I additionally combined the aircaft make and model columns to create a 'Combined' column since each aircraft model is unique to a particular make. I utilized this column to uniquely identify each craft.
```Python
df['Combined'] = df['Make'] + ' ' + df['Model']
```
Run each remaining cell to either see summary statistics, descriptive statistics, or the first 5 values of the sampled dataset used the .head() method.
With this preparation, I was able to make visualizations with Matplotlib to determine Injuries caused by an aircraft, their severity, and make recommendations based on Engine type and Number of Engines.

## Repository Navigation Instructions
This repository contains several files and folders.

The project.ipynb is the notebook with the relevant code used to analyze the dataset.

The 'Excel sheets-data' folder has the original Aviationdata spreadsheet, the USCodes, and the sampled dataframe spreadsheet.

The 'Presentation.pptx' is a ppt document with the summary presentation of the project and recommendations based on the data analysis.

The link to the tableau dashboard and story are [here](https://public.tableau.com/views/Dashboard_17458785633440/Story1?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link).


