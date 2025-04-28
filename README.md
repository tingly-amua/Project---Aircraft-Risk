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
These are the packages i used in data analysis and visualization:




