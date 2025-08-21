# power-bi-dates-design-pattern
Power BI Dates Design Pattern - a solution for use with [Power BI Desktop](https://www.microsoft.com/en-au/power-platform/products/power-bi/desktop). 

## What is this template for

This Design Pattern provides a generally applicable "Dates table" design that will suit almost all Power BI datasets/reports.  

A "Dates table" is one that contains a row for every date, spanning all the years of interest in a given dataset.

Even the simplest Power BI dataset/report can benefit from a Dates table, for functionality such as:

- Creating relationships between independent tables of data by Date. With the Dates table in place, you can build your Slicers, chart Axes etc on the Dates table columns, knowing they will apply consistently to data from any related table.     

- "Relative Time": e.g. Current Day, Current Year, Month-to-Date (MTD), Year-to-Date (YTD).  These fields can be used to set Slicers or Filters that you can then forget - they will automatically roll forward each time you Refresh. Default "Current Date" is the end of the prior month, but that can be adjusted in the query step "Added Current Date".

- Predefined calculations for commonly-needed fields e.g. Day Name, Week No, Year-Month, Year-Quarter. Avoid the hassle and inconsistency of ad-hoc calculations.

## How to use this template:

If you are starting a new Power BI Desktop project, then simply start by opening a copy of the PBIX file in this Design Pattern, using [Power BI Desktop](https://www.microsoft.com/en-au/power-platform/products/power-bi/desktop).

Use **Home, Transform data, Edit parameters** to adjust the settings to suit your scenario. The impact of each is described below, and also in the Parameter descriptions.

- **Year** - Enter the first year for your Dates table. 
- **Month** - Enter the first month for your Reporting Year. For example, if your Reporting Year starts on 2025-07-01, the month value is: 7.
- **Language** - Select the language for the Month and Day name. Languages available in the drop down list: en-US (english), es-ES (spanish), zh (chinese), fr (french), de (german) and hi (hindi)
- **StartWeekDay** - If your week starts on Monday select 1 and if your week starts on Sunday select 0

If you want to integrate this Design Pattern into an existing file, then follow these steps:

- Open this Design Pattern and your file in 2 Power BI Desktop Windows. Open the **Edit Queries** window in each.     

- Right-click the **Dates** query in the Queries list (from this file) and choose Copy. Switch to your file and Paste into Queries list. This will include the dependent Parameters.

- Edit the Parameter values to suit your requirements.  Hit **Close & Apply** to run the Query

- Back on the main window in your file, go to the Fields pane and hide all the Fields ending with "Sort", also the "Reporting Date" field. If your Month parameter is set to 1 (January Reporting/Financial Year) then hide all the Fields beginning with "Reporting".

- From the **Modeling** ribbon, apply each "Sort" field as the **Sort By Column** for the field with the matching name, e.g. select **Current Day** and set the **Sort By Column** to: **Current Day Sort**. Select the **Date** field and set Formatting properties to suit your requirements.

- From the **Relationships** window, add relationships between the Date column and your equivalent date columns in your other Tables.


