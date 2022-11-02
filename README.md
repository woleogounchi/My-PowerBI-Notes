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

## The Data Analytics Pipeline with Power BI

### 1. Data Check (Data Quality & Integrity Check)
Data Quality Check is a process that checks the data for errors and inconsistencies.
E.g. missing values, duplicate values, invalid values, etc.
We could also do a sense check with other internal data sources.

### 2. Data Exploration
Exploring the data means asking ourselves a set of questions:
E.g. Does an increase in revenue also lead to an increase in profits?

### 3. Data Analysis & Visualization
This step consists in analyzing the data, choosing and creating the right visualizations in order to convey a message.

### 4. Dashboarding
Here we combine our visualizations and analysis to create one or more dashboards.
  
### 5. Commucating Insights/Reporting
In this last step, we will create a report that will communicate our insights to stakeholders.

## Data Preparation

### Transforming text in Power BI
 * We consider a clean text data when it is free of typos (it is recommended to fix those errors in the source file as possible before loading the data into Power BI). 

 * The data should be consistently formatted meaning that the same data should not be represented in different ways, use uniform capitalization, avoid leading and trailing whitespace, same for punctuation (!) or control characters (\n, \r, etc.).

 * Each column should only store one piece of information. For example, if a column stores the name of a person, the column should not store the age of the person. Therefore, columns should be either split or mergeed to achieve this outcome.

#### How to clean text data in Power BI
* [Clean text data in Power BI - Microsoft Docs](https://docs.microsoft.com/en-us/power-bi/data-preparation/clean-text-data-in-power-bi)

* Accessed from the *Transform* ribbon, use the *Format* option to change the capitalization and access *Trim & Clean* to remove leading and trailing whitespace with *Trim* and remove control characters (new line, carriage return, etc.) with *Clean*. *Trim & Clean* should be applied to all text columns.

### Numerical transformations in Power BI

* The 1-10-100 rule: States that it costs $1 to a Data Analyst to verify that a single row of data is valid, it costs $10 to clean that row if any missing or incorrect data is found, and it will $100 if the data is not cleaned and left as is.

* Ideally, numerical columns should be free from missing values and errors so that measures built with DAX would function properly. Outliers will also affect our analysis, but will require more advanced tools.

* [Numerical transformations in Power BI - Microsoft Docs](https://docs.microsoft.com/en-us/power-bi/data-preparation/numerical-transformations-in-power-bi)

* One of the most applied mathematical transformations is the **Absolute Value**. This transformation is used to remove negative values from a column.

* **Logarithmic Transformation (Natural/Base 10)**: This transformation is used to transform a column into a logarithmic scale. It allows to translate an exponential relationship into a linear one. It's an advanced transformation that will only be applied if we have a good mathematical and statistical basis for using it.

* **Multiplying by / Adding a scalar value**: can also be done with Power Query's numerical transformations.

* **Rounding** our data in Power Query allows to save memory and make the columns of our datasets more readable by reducing the amount of decimal places. This comes in handy when we have huge datasets with a lot of rows.
[Rounding in Power BI - Microsoft Docs](https://docs.microsoft.com/en-us/power-bi/data-preparation/rounding-in-power-bi)

#### Date & Time transformations in Power BI
Date and Time are considered as a special type of numerical data in Power Query.
Special transformations could be applied to date and time columns. Such as:
- Extracting the year, month, day, hour, minute, second, etc.
- Start/end of the year, quarter, month, week, etc.
- Extract age 

## Data Transformation

### Data Transformation in Power BI
Data transformation is the process of converting data from one format to another. It is a crucial step in the data analytics pipeline as it allows to prepare the data for analysis and visualization.

### Dataset shapes
A dataset could take 2 main structures:
- **Wide**: Each column represents a different variable and each row represents a different observation.
- **Long**: Each column represents a different observation and each row represents a different variable.

### Data Shaoe Transformation in Power BI
There is 2 ways to transform the shape of a dataset in Power BI:
- **Pivot/Unpivot**: Transforming a **long disaggregated dataset** into a **wide aggregated dataset** and vice versa.
- **Transpose**: which means to swap the rows and columns of a dataset.
* [Data shape transformation in Power BI - Microsoft Docs](https://docs.microsoft.com/en-us/power-bi/data-preparation/data-shape-transformation-in-power-bi)

### Group by Transformation in Power BI
Grouping allows to aggregate our data by changing the granularity of our dataset. It is a very useful transformation that allows to reduce the size of our dataset and to make it more readable.
After choosing a granularity, we can apply an aggregation function to our data.
There is many aggregation functions that we could apply:
- **Count**: Counts the number of rows in a group.
- **Count Distinct**: Counts the number of distinct values in a group.
- **Sum**: Sums the values in a group.
- **Average**: Calculates the average of the values in a group.
- **Min**: Calculates the minimum value in a group.
- **Max**: Calculates the maximum value in a group.
- **Median**: Calculates the median value in a group.
- **Mode**: Calculates the mode value in a group.
- **StDev**: Calculates the standard deviation of the values in a group.
- **Ect.**
- **Custom Aggregation**: Allows to create our own aggregation function.



## Data Modeling

### What is a data model?
A data model is a representation of the data in a database (aconceptual view of data elements). It is a logical representation of the data and how it is related to each other (typically a visual representation). It is a blueprint of the data that will be stored in the database.
Data models include:
- **Entities (tables)**
- **Attributes (columns)**
- **Relationships (foreign keys)**
- **Constraints (primary keys)**
- **Hierarchies (parent-child relationships)**
- **Data types**

### Data Modeling in Power BI
Data modeling consists in building a Data Model and in Power BI, that process is managed by **Power Query**, which is a tool that allows to import data from different sources, transform it and load it into the data model.

### Database normalization
Database normalization is a set of logical rules and processes that allows to reduce data redundancy and improve data integrity. 
It is a process that consists in dividing a large table into smaller tables and defining relationships between them. It is a process that is applied to relational databases.

### Data shaping in Power Query
Power Query includes several data shaping operations to get closer to a normalized data model. These operations are:
1. **Column splitting**: breaks one column into multiple columns based on split criteria (like after a delimiter such as comma or tilda, or splitting after a set number of characters).
2. **Column extraction**: takes a column from table and breaks them out into multiple tables. Keep a key on the original table to know which values fit together.
3. **Query merging**: joins together two existing tables based on values from one or more columns (Types of joins: inner, left outer, right outer, full outer).
4. **Query appending**: combines contents of two table into a single table. It matches rows based on column names adding NULL for missing columns. It's equivalent to a UNION ALL in SQL.

### Dimensional modeling
Also called **The Kimball Model**, it comprises 2 key concepts:
- **Facts**: numerical values that are measured and are the basis of our analysis (i.e. metrics from a business process).
- **Dimensions**: attributes that describe the facts (i.e. the date, the product, the customer, etc.), they basically provide context surrounding a business process.
Those 2 concepts combine to form the **Star Schema**, a data model used to represent the relationships between facts and dimensions. Star shemas are used in data warehouses and are a very common data model used in the business intelligence industry. Power BI is optimized to use star schemas over any other ways of loading data.

#### Fact tables
Fact tables are typically composed of 2 columns:
- **Facts (measures)**: measurements or metrics from our business process (e.g. sales, employee counts or number of website visits).
- **Keys**: used to establish relationships between fact tables and dimension tables.

#### Dimension tables
Dimension tables provide context around facts. They are shared business concepts (e.g. person, employee, customer, vendor). They contain static or slowly changes data (e.g. name, date of birth or height).

### Snowflake schema



