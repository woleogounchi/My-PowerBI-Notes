# My-Power-BI-Notes
Those are my notes on learning PowerBI.

## What is PowerBI?
PowerBI is a Microsoft data visualization and analytics platform that allows to interactively explore data to gain insights.
it enables you to effectively report insights through easy-to-use customizable visualizations.

## Transforming Data
Raw data usually does not arrive in the perfect form when accounting for things like human errors, bugs, and file conversion. Power BI accounts for this with the Power Query Editor which allows to transform data before loading them.

## DAX
DAX stands for **Data Analysis eXtension**. It is a formula language used in Power BI that provides the ability to create columns, tables, and measures.
DAX is also used in other Microsoft tools including Analysis Services and Power Pivot.
DAX has over 200 different functions that fall into several categories:
- **Aggregation**: Functions that aggregate data (Ex: `SUM()`, `COUNT()`, `AVERAGE()`);
- **Date and Time**: Functions that manipulate date and time (Ex: `TODAY()`, `MONTH()`, `YEAR()`);
- **Logical**: Functions that operate on logical values (Ex: `AND()`, `OR()`, `IF)`);
- **Text**: Functions that operate on text (Ex: `CONCATENATE()`, `LEFT()`, `UPPER()`);
- **Ect..**: and many other functions that could be found in [DAX function reference - Microsoft Docs](https://docs.microsoft.com/en-us/dax/dax-function-reference).

## Calculated columns vs. Calculated measures
* **Calculated columns**:
  - For evaluating each row
  - Add a new column in an existing table
  - Calculated at **data load** and when the data is refreshed
  - Stored in memory: pre-calculated and appended to each row in a table and stored inside the data model

* **Calculated measures**:
  - For aggregating multiple rows
  - Results in another field that you can add to a visualization
  - Calculated at ***query time** as you interact and filter
  - Not stored in memory: Makes use of CPU and is re-calculated every time a filter/slicer changes

## Context in DAX 
In DAX, context enables dynamic analysis where results of a formula change to reflect the selected data.
There are 3 types of context: **row**, **filter** and **query**.

## Quick Measures in DAX
Quick Measures are a really powerful feature in DAX that allows to carry out complex calculations without needing to write the code fromm scratch. Basically, a quick measure will run a set of DAX commands behind the scenes and then will present the result to use in the report. Learn [more...](https://docs.microsoft.com/en-us/power-bi/transform-model/desktop-quick-measures).



