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

  * **Calculated measures**:
    - For aggregating multiple rows
    - Results in another field that you can add to a visualization
    - Calculated at ***query time** as you interact and filter


