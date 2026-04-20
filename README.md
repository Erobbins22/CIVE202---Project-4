# CIVE202---Project-4

## Project Description
Natural disasters can have a big impact on communities, they bring out great property and economic loss and often death tolls (Natural Disasters: What They Are, Causes and Characteristics, n.d.). They are caused by the occurrence of an extreme natural phenomenon that affects negatively in a given area. Because of this Risk Averse, LLC, an independent risk analysis consulting group, asked our group of engineers for an analysis of natural disasters risk in two states: Oklahoma and Wyoming. 

The Department of Homeland Security for the Federal Emergency Management Agency (FEMA) developed the National Risk Index (NRI) which measures the relative risk of natural disasters across the United States. The NRI dataset can help find Expected Annual Loss, Social Vulnerability, and Community Resilience. However, the risk defined in the NRI dataset may not always represent real world conditions, and some factors may be looked at differently or not as much importance. Risk Averse, LLC tasked our team to research and create alternative risk methods that can use the NRI dataset as input, but also proposing a new definition that is understandable and readable to ordinary people. In this project, we analyze disasters for Oklahoma and Wyoming and created our own definition of risk that focuses on hazard exposure. To complete our give task, our team used the NRI and Social Vulnerability Index (SVI) dataset, which was cleaned, organized and combined to ensure accurate results, and handle missing values. Using tools like GeoPandas, we created maps, tables, and graphs to visualize and compare the original NRI results with our new model. This report will explain the methods we used to complete the analysis. Overall, this project helps highlight the importance of how risk is defined and measured and how definitions can impact decisions like supporting communities or planning disasters. 


---
## Repository Structure

- [Project 4 Code](CIVE202_Spring2026_Project4_Group415108_Code.ipynb): This is the code that contains all the data analysis, visualization code, and IDM simulation. 
- [Definition of Risk](Definition_of_Rish_(New).docx):Dataset containing United States transportation usage characteristics. 
- [Geopandas Investigation](Geopandas_Investigation.docx):Dataset containing high-resolution vehicle trajectory and driving behavior data.


All the data below is the exported plots:

-[Gantt Chart](CIVE202_Spring2026__Project4_Group415108_Ganttchart.xlsx),
[Engineering Timesheet](),
[Figure 1 - Risk Rating Distribution](figure1_rating_distribution(1).png),
[Figure 2 - Scatter Plot](figure2_scatter(3).png),
[Figure 3 - Risk Map](figure3_rish_map(2).png),

---
## User Guide

### 1. Program Overview
This notebook automates the loading, cleaning, and joining of NRI and SVI datasets for two states, computes an alternative risk index, generates summary visualizations, and produces a GeoPandas choropleth map. The analysis is designed to help Risk Averse, LLC identify potential categorical bias in the NRI scoring methodology.
### 2. Data Requirement 
- [NRI Data Dictionary.csv](NRIDataDictionary.xls) - FEMA NRI Metadata
- [Wyoming.csv](Wyoming.xls) - CDC/ATSDR SVI - Wyoming
- [Oklahoma.csv](Oklahoma.xls)- CDC/ATSDR SVI - Oklahoma
- [tl_2022_56_tract.zip](tl_2022_56_tract(1).zip) - Census TIGER/Line Shapefile - Wyoming tracts
- [tl_2022_40_tract.zip](tl_2022_40_tract(1).zip) - Census TIGER/Line Shapefile - Oklahoma tracts

### 3. Execution Sequence
- Data Loading & Filtering — The notebook loads the full NRI Census Tract CSV and filters for Wyoming and Oklahoma.
-Dataset Joining — NRI and SVI datasets are merged on the STCNTY key. The NRI data dictionary is loaded for reference.
-Missing Value Handling — Sentinel values (-999) are replaced with NaN; numeric NaNs are filled with 0; string NaNs with 'Unknown'.
-Alternative Risk Index — A new risk score is calculated for each tract as Hazard Exposure / (Resilience Score + 0.01), normalized to 0–100.
-Summary Figures — Figures 1 and 2 are generated comparing NRI and new risk ratings/scores.
-GeoPandas Map — Census Tract shapefiles are loaded and joined to risk scores to produce Figure 3.
-Bias Analysis — Categorical agreement and disagreement between the NRI and the new index are quantified.


### 4. Methods
- All analysis was performed in a Jupyter Notebook using Python (pandas, NumPy, Matplotlib, Seaborn, GeoPandas).
-The alternative risk index formula: Risk = Hazard Exposure / (Resilience Score + 0.01), where hazard exposure is the sum of (annual frequency × expected annual loss) across 6 key hazards: wildfire, severe wind, drought, tornado, winter storm, and hail.
-Community resilience is a composite of four min-max normalized sub-scores: SVI Theme 1 (economic stability, inverted), SVI Theme 2 (social connectedness, inverted), NRI Community Resilience Score (direct), and NRI Social Vulnerability Score (inverted).
-Final scores are normalized to 0–100 for direct comparison with NRI percentiles, and rated using NRI's five-tier system: Very Low → Very High.
-The categorical bias analysis identifies Census Tracts where the two methods disagree (e.g., NRI rates High while the new index rates Low, or vice versa).


---
## Project Goals
The goal of this project is to evaluate the National Risk Index (NRI) and determine how risk is calculated across communities. This will be done by developing an alternative risk model and comparing the NRI data that can be compared between the original NRI framework and our proposed definition of risk. Using data from two selected states which our group of engineers decided on Oklahoma and Wyoming, the project aims to identify differences in how risk is measured and determine whether the current NRI method may contain bias or overlook factors that are important in analyzing natural disasters. By comparing both models, our team seeks to better understand how changes in risk definition can impact which communities are most vulnerable. To achieve these project goals, several key steps will be completed by the engineering team. First, we will download, clean and organized census tract-level data for Oklahoma and Wyoming from the Federal Emergency Management Agency (FEMA) National Risk Index (NRI) website and download the Metadata files to clarify the variables. The team will then handle any missing or incomplete data to ensure accuracy. After preparing the data, our team will then generate two summary tables and create a map using GeoPandas to clearly communicate risk information and highlight differences between the two approaches. 




---
## Project Documentation
Links:
- [Scope of Work](CIVE202_Spring2026_Group415108_Project4_SOW(1).docx)
- [ACD](CIVE202_Spring2026_Group7_Project3_ACD.docx)
- [Written Report](CIVE202_Spring2026__Group415108_Project4_Report.docx)


