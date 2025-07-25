# People_Counter

## The People Counter project has three major components:
### 1) R Script
The People_Counter.Rproj file opens an R project that helps the user create a series of processed datasets from the raw dataset imported from eco-visio (Eco-visio is the platform that manages people counter data). The created processed dataset can then be used for analysis in the PowerBI dashboard. The PowerBI.Rmd script allows the user to process raw people counter data and outputs processed files in the Data/Processed/PowerBI folder. Note that processed datasets can also be used for analysis separate from the powerBI dashboard.

### 2) Power BI Dashboard
The power BI Dashboard lives in the People_Counter root folder. It allows users to select date range, counter, weekday/weekend to see usage trends. The counts utilze the 'OUT' count of all the counters. This ensures that counters are not double counting, meaning it does not count the "IN" and the "OUT".The dashboard has three pages.

1) The first 'Macro Trends' page allows user to see ALL the collected data from all counters. It also tallies the total trail usage counts since the counters started recording.
2) The second page named 'Weekly Trends' shows the trail usage broken down by weekday. It is mainly intended for the user to see how trail usage changes depending on day of week. You can sort by counter, date range, weekend/weekday.
3) The third page named 'Annual Projections' shows the annual trail use prediction based on available data and extrapolation. This does not account for seasonality. It is a simple average daily usage calculation multiplied by 365.

### 3) Data folder
The data folder contains a Processed folder, Raw folder. The raw data downloaded from eco-visio should go in the Raw folder

## Process for downloading data from eco-visio
1) Go to https://www.eco-visio.net/
2) Log in with credentials
3) Go to 'Analysis' tab
4) Click on 'Period' and change selection to 'Manual Selection'.
5) Set custom date range from 5/7/2025-xxxx. Replace xxxx with the most recent date. Click 'OK'
6) Do not change the 'Sites'. Keep at 'Whole Domain'
7) Click 'Time Series'. Keep the 'Type of Graph' on 'Curve'. Change the 'Interval' to 'Hour'. 'Keep 'Show Events'
8) Click on 'Show More', and toggle on 'In' and 'Out' and toggle off 'Total'
9) Click on 'Table' at the top right
10) Click on 'Download'
11) Save the file in the appropriate location as csv with the appropriate naming convention. Location, something like- C:\Users\tkatayama\OneDrive - DOI\Documents\Projects\R\People_Counter\Data\Raw
12) Naming convention: All_20250507-mmdd.csv
13) Change mm and dd to appropriate two digit month and date

## Process for Updating Dashboard
1) Save new raw data file in the Data/Raw folder.
2) Update the file_path in the PowerBI.Rmd R script
3) Run PowerBI.Rmd R script in RStudio
4) Open your Power BI file
5) Click Home -> Refresh
6) Your dashboard automatically updates with new data!
7) Verify that the "Last Updated" Card shows latest update
