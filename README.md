# Media-Campaign-Data-Validation-And-Analysis-Using-Microsoft-Excel-And-Power-BI
In this project I validate and analyze data on the media campaign of a client from the year 2015 to 2019.
The data on the media campaigns are stored in two Excel sheets. The first sheet contains raw data on:
1. Date
2. Campaign
3. Cost
4. Impressions
   
The second sheet contains campaign lookup data. This lookup data contains information on each specific campaign.
1. Campaign
2. Channel - Values in this column represent media campaign channels utilized during the period of the campaigns. These channels are Facebook, Display, PLA (Product Listing Ad), PPC (Pay-Per-click)
3. Brand/Generic
4. Type - The values in this column represent the type of campaign undertaken. The types are Prospecting and Remarketing campaigns.

## Data Merging Process
Both tables were merged using the campaign column which is found in both tables.
Each campaign information in the raw data sheet was matched to its respective channel, brand type and campaign type from the campaign lookup sheet.
The information from both were merged into a new data sheet called campaign_data.
1. To match each campaign to its respective channel the following excel formula was used:
```=INDEX('Campaign Lookup'!B:B,MATCH(B2,'Campaign Lookup'!A:A,0))```

2. To match each campaign to its respective brand type (Brand/Generic) the following excel formula was used:
```=INDEX('Campaign Lookup'!C:C,MATCH(B2,'Campaign Lookup'!A:A,0))```

3. To match each campaign to its respective campaign type (Prospecting/Remarketing) the following excel formula was used:
```=INDEX('Campaign Lookup'!D:D,MATCH(B2,'Campaign Lookup'!A:A,0))```

4. To retrieve the campaign month the following excel formula was used:
   ```=MONTH(A2)```
   
5. To retrieve the campaign WEEK the following excel formula was used:
   ```=WEEKNUM(A2) - WEEKNUM(DATE(YEAR(A2),MONTH(A2),1))+1```

6. To retrieve the campaign year the following excel formula was used:
   ```=YEAR(A2)```

## Data Cleaning and Transformation
The following data cleaning and tramsformation processes were undertaken to make the data accurate and fir for analysis.
1. Removed the dates attached to 22 campaign names in the campaign coulmn.
2. Removed 778 Facebook and Instagram related posts in the campaign column.
3. Removed all data related to Facebook page likes.
4. Removed all data related Facebook post engagement likes.
5. Replaced all spaces in campaign names with underscores, colons with pipe symbol, and removed square brackets and parenthesis.
6. Corrected spelling in campaign names to ensure uniformity.
7. Extracted the week, month and year information from the date column and stored each in separate columns.
8. Removed all campaign information that had both cost and impressions recorded as 0.
9. Rounded up all decimal point impression values to the nearest whole number.

## Data Validation and Analysis Project Files
- The file ```Data Validation (Econometrics).xlsx``` is the excel file containing the project instructions/guidelines sheeet, raw data sheet, campaign lookup sheet and campaign_data sheet containing the merged data from the raw data sheet and campaign lookup sheet.
- The merged infromation in the campaign_data sheet was copied and moved a new excel workbook called ```media_campaign.xlsx```.
- The ```media_campaign.pbix``` file is the Power BI data visualization file which you must download onto your local machine or PC and open with the Power BI desktop application to view the interactive visual dashboard for this project.
- The Power BI report dashboard can also be viewed by clicking on this [link here](https://app.powerbi.com/groups/me/reports/94598379-5abb-4dd2-adc3-bb8d02fbab96?ctid=afab14ca-ab60-42a6-8a29-ff101424f318&pbi_source=linkShare).
- The file ```DATA VALIDATION & ANALYSIS PRESENTATION.pptx``` is the PowerPoint presentation deck of the data validation process and analysis.

