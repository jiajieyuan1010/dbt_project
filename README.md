**ANALYTICS ENGINEERING WITH AIRBNB:**

This is an end-to-end analytics engineering project. Utilizing Airbnb data, I built an ELT (extract, loading, transform) pipeline with DBT, store raw data in Snowflake, and prepare formatted data for visualization using Preset.

 * Tech stack: snowflake(data warehouse), dbt(data build tool), preset(visulization tool)
 * Data source: Inside Airbnb: Berlin
 
**PROJECT:**

I leverage various functionalities of dbt to transform and format raw data stored in Snowflake, thereby enhancing the data's usability for further analysis and visualization.

<img width="1194" alt="tech stack" src="https://user-images.githubusercontent.com/111074755/205756349-666f3c16-1ad1-44e6-91c2-0bd2ffbf9d08.png">
 
 The dbt functionalities used in this project: 

 * dbt Models - data model are core components of dbt. It is used to convert raw data to tables using sql.
 * dbt Materializations - four types
 1. View: dbt creates a database view with your SQL statement. The database reruns this SQL each time the view is queried.
 2. Table: dbt creates a database table with the result of your SQL statement. Unlike views, tables physically store the data in the database.
 3. Incremental: dbt updates an existing table with new data, based on your SQL statement. It's efficient for large tables with frequent, minor updates.
 4. Ephemeral: dbt doesn't create a database object. It uses your SQL statement as a subquery in other models. This is useful for intermediate transformations.
 * dbt Tests - two types
 1. Schema tests: These are pre-defined tests that are configured in the schema.yml file. They include tests like unique, not_null, accepted_values, etc. For example, you can ensure a column has unique values or that a field never contains null values. (dbt_expectations is a dbt package that provides a set of predefined data quality tests based on the concept of "Great Expectations," a Python-based open-source data validation library.)
 2. Custom data tests: These are tests that you define yourself, written as SQL queries in separate .sql files. A custom data test should return no rows if the test passes. If rows are returned, these represent test failures. This allows you to create very specific and complex tests based on your business rules or data integrity requirements.
 * dbt Documentation
 1. Models: Shows the structure of your transformed data (tables and views) including their columns, data types, and descriptions.
 2. Tests: Shows the data quality tests you've set up in dbt, and their results.
 3. Lineage Graphs: Visualizes how all your models are related and their dependencies.
 4. Sources: Shows the raw data sources that your dbt project uses.
 5. Macros: Lists custom macros used in your project, if any.
 * dbt Sources - In dbt, Sources represent the raw data that exists in your warehouse before dbt runs. They help dbt track where your data comes from and how fresh it is.
 * dbt Seeds - Seeds are a way to load data from csv files into your database to be used in transformations. They're useful for small reference data like lists, mappings, or parameters.
 * dbt Snapshots - In dbt, Snapshots capture the state of your data at a specific point in time and allow you to track changes to your data over time, essentially providing a historical record of your data.
 * dbt Hooks and Operations
 1. In dbt, Hooks are custom SQL statements that run at specific times in the dbt execution process, like before or after a model is created. They're used for tasks like granting permissions or setting up database specifics.
 * Jinja and Macros - Macros are custom functions that can be used in SQL. They can be used to reduce duplicated code, improve readability, and create reusable components.
 * Analyses, Exposures 
 1. In dbt, Analyses are SQL queries that don't create a table or view in your database, but are stored in your project for ad-hoc analysis and exploration.
 2. Exposures help dbt understand and document where dbt models are used in your organization, such as in BI tools, other applications or data science projects. They provide visibility into downstream dependencies.
 * Data Visualization (Preset)
 
 
**PROJECT REQUIREMENTS**
 
* Changes in modeling are easy to track and revert.
* Dependencies between models are explicitly stated.
* Provides a way to explore interconnections between models.
* Includes data quality tests for robust validation.
* Provides efficient error reporting for easier debugging.
* Supports incremental loading of fact tables to manage data volume.
* Provides tracking of historical changes in dimension tables.
* Provides accessible and understandable documentation.
 
**DATA MODEL**

<img width="984" alt="Data Model" src="https://user-images.githubusercontent.com/111074755/205756570-9c0a6932-d5f6-4653-b3f6-3c7426f60293.png">

**DIRECTED ACYCLIC GRAPH**

<img width="1184" alt="Data Flow" src="https://user-images.githubusercontent.com/111074755/205756792-a4d7750b-e265-451a-ac5e-0ca86e73299d.png">


**DATA FLOW STAGING LAYERS**

<img width="1174" alt="Data Layer" src="https://user-images.githubusercontent.com/111074755/205757127-ba1947dc-9889-4d71-a7f8-5720cca8acdb.png">

**BI DASHBOARD**

<img width="1467" alt="Dashboard" src="https://user-images.githubusercontent.com/111074755/205765072-2a14c438-93e7-4c8d-a330-2931bd240c68.png">
