# 01 Configure a Semantic Model

Date of annotation: 2025-11-09

## 01 Introduction

- the semantic model is designed once Power Query queries are applied.
- semantic model supports reporting requirements
- criteria of the semantic model is that it is user-friendly and intuitive.
- semantic model == semantic layer.
- semantic layer lays on top of the data, providing a user-friendly and intuitive interface.
- designing the semantic layer involves the following:
  1. configuring relationships between model tables
  2. setting table and column properties to enhance model design
  3. adding other model objects: hierarchies, measures, and parameters.

## 02 Configure Relationships

Submodule summary: This submodule describes the basis and configuration of model table relationships. it touches on cross-filter configuration, cross-filter paths, active and inactive relationships and how to interpret and use the model diagram.

submodule introduction notes:

- ensuring model table relationships are properly configured is important.
- table filters can be propagated along relationships to other tables.

### 01 Configure Data Load Options

- _Data Load_ contains settings relevant to relationships.
- options include: 'import relationships from data sources on first load', 'update or delete relationships when refreshing data', and 'autodetect new relationships after data is loaded.'
- These settings should be selected before Power Query queries are applied.
- Relationships can be created in 'Manage relationships' window or in Model view.
- tables that are part of the model but don't need relationships to other tables are called _disconnected tables_.
- A disconnected table can be used to support what-if scenarios, or for field parameters.

### 02 Columns

- Relationships consist of a 'from' column and a 'to' column
- these two columns need to be of the same data type and contain unique values.
- relationships can only consist of 1 column on either table.
- if a table has a multi-column key, it needs to be represented by an appropriate single key column that preserves the uniquness.
- data types can be adjusted in Power Query.

### 03 Understand Cardinality

- there are 4 kinds of relationships:
  - one-to-many
  - many-to-one
  - one-to-one
  - many-to-many
- automatic relationship detection is based on the data Power BI can see.
- if later data breaks the detected cardinality, the user will need to adjust the relationship detection settings.
- one-to-many and many-to-one are each the inverse of the same relationship (herearefter referred to as one-to-many).
- one-to-many most common relationship
- one-to-many used to relate dimension tables (one) to fact tables (many) in star schema.
- one-to-one less common as better design to combine tables with one-to-one relationship, reducing model complexity.
- many-to-many used for more complex relationships, connecting across levels of granularity etc (JS - find more examples).

### 04 Understand Cross Filter Direction

- part of relationship definition is cross-filter direction.
- cross-filter direction defines how filters propagate.
- if a cross-filter encounters a 'one' side it will always propagate to the other side.
- if cross-filter encounters 'many' side, user must select to propagate.
- options are as follows:
  - for one-to-many: choose one direction or both directions.
  - for one-to-one: both directions (no options)
  - many-to-many: single to either table, or both.
- best practice to minimize 'both' as it impact performance, also one direction is more intuitive (defines a hierarchy).
- both direction may be used in many-to-many analysis i.e. salespeople assigned to multiple regions, region can have multiple sales people.
- a many-to-many analysis needs a bridging table containing the keys to both sides.

### 05 Active vs. Inactive Relationships

- one one filter propagation path can be active at any time.
- if a model could contain multiple valid paths, one must be set to active and the others to inactive.
- this permits the storage of those defined paths.
- a dimension table that can filter a fact table in different ways is called a _role-playing dimension_.
- An example is a `Date` table that is related to two parameters in the fact table: `OrderDate` and `ShipDate`. Depending on requirements the filtering via `OrderDate` will be different to filtering via `ShipDate`.
- To enable multiple filtering by a role-playing dimension the relationship between the dimension and the fact table must be through bridging tables so that the relationships are distinct.
- in the example above, `OrderDate` and `ShipDate` become `Order Date` and `Ship Date` and have active relationships to the fact table. The path becomes `Date/Order Date/Sales` and `Date/Ship Date/Sales` as opposed to two conflicting `Date/Sales`.

### 06 Working with the Model Diagram

- model diagram
- relationships are created by dragging and dropping the columns between tables.
- relationships are edited by double clicking on them.
- cardinality is displayed through a '1' or '\*' at the end of the relationship lines.
- cross filter direction is displayed by an arrow on the line.
- active relationships are solid, inactive are dotted.
- cursor hove over relationship shows the related columns.

## 03 Configure Tables

### 01 Configure Table Properties

- table configuration:
  - table configuration can be accessed from the ribbon, data pane, or model diagram (properties pane).
  - microsoft recommends the model diagram (properties pane) approach because multi-select and bulk-property updates possible from here.
- table properties:
  - Name:
    - a tables default name is linked to the name of the PQ query that generated it. The relationship is two-way so if the column is renamed the query is too.
    - tables can be renamed through Name property.
    - table names must be unique.
    - table names should be user-friendly.
  - Description:
    - descriptions are optional
    - descriptions are used to provide detailed defintiions of the table.
    - report authors can see the definition when hovering over table in Data pane.
  - Synonyms:
    - allows setting of multiple alternative names for a table.
    - primarily for Q&A AND Copilot to handle requests for automatically generated visuals or DAX formulas.
  - Hidden:
    - tables can be hidden from the Data pane.
    - developer specific objects such as bridging tables should be hidden.

### 02 Mark Date Tables

- Auto date/time: automatically creates hidden date tables for each date/time column
- bad practice (?) better to create own tables from source data or DAX calculated table when mark as date table.
- this is better for DAX time intelligance functions.
- Marking a date table is done from the more options ellipsis menu in the Model view.
- a date column must be selected to complete the setting.
- on selection, the column will be validated.
- validation requires: values are unique, no blank, values are contiguous from start to finish.

## 04 Configure Columns

This submodule discussed the various properties and configurations of columns.

### 01 Intro

- columns properties include: name, description, synonym, is hidden.
- common to hide relationship columns especially when value is not meaningful.
- column names must be unique.
- visible columns should have user friendly names.
- when columns are renamed a modify name step is appended to the source Power Query.
- display folders can be used to organise table fields.
- display folders should be used if a table has many visible fields.
- display folders are created by selecting the desired fields in the Data pane then adding the name in Properties pane / Display folder. This will then appear in the Data pane (wtf.)

### 02 Configure Column Formatting

- each column has a data type
- data type is inherited from PQ
- if data type changed in PBI, a change data type query is appended in PQ.

### 03 Set Sort Order

- PBI has natural sorting but custom sorting is achieved by setting Sort by Column property ( doesnt appear to be present in web app version).

### 04 Categorize Data

- data categories are used for more complex data that is represented in a primative form i.e. spatial data represented by floats.
- categorires help PBI better work with the data.

### 05 Set Summarization

- Numeric columns have built-in summarization options.
- choosing the `summarize by` determines how the column summarizes by default.
- options include: Sum, Min, Max, Av., Count, Discount Count, None.
- Sigma symbol used to label columns which are summarizable.
- report authors can select summarization method when used by a visual.
- meaures can further be used to determine how numeric columns are summarized.

## 05 Configure Heirarchies

### 01 Intro

- Hierarchies are optional.
- Hierarchies model the hierarchy between columns of a table.
- tables can have multiple defined hierarchies.
- hierarchies are restricted to columns from one table.
- they provide a navigation path across the columns.
- hierarchies can have descriptions, synonyms, display folders and 'is hidden'.

## 06 Configure Measures

### 01 Intro

- complex summarization is achieved with a _measure_.
- measures are named DAX formulas.
- measures are listed in Data pane one created, labelled with a calculator icon.
- measure names must be unique within the model namespace.
- measures are essentially custom calculations beyond the scope of simple summarization.
- measures enable effective data visualisation.
- _Copilot for PBI_ and _Quick measures_ can be used to generate measures.

### 02 Use Quick Measures

- How to use Quick measures:
  - select a calculation template
  - drag fields to configure the measure.
  - PBI creates the measure based on input.
- after configuration a measure can be treated like any other column, with a description, synonyms, display folders, is hidden, formatting, etc.
- measures can be reassigned to different tables with the "Home table" property.
- Copilot can autogenerate descriptions based on the DAX formula.

## 07 Configure Parameters

### 01 Intro

- A _parameter_ can be used to change report settings like filters or calculations without modifying the data.
- there are two types or parameterL: numeric range and fields.

### 02 Create a Numeric Range Parameter

- _Numeric range_ are like SQL sequences:
  - require a numeric data type
  - minimum and maximum values.
  - increment value.
  - default value.
- after configuration, PBI calculates the values of the range in a table with DAX and adds a measure to filter the table.
- The Numeric range table begins life as a disconnected table.
- numeric range parameters can be used in what-if schenarios. i.e. they provide a range of values to perform calculations on, such as displaying the effect of changing a parameter in a calculation.
- Parameters are displayed in the Data pane with a qustion mark (?).

### 03 Create a Fields Parameter

- A _Fields_ parameter is a group of different fields.
- Fields can be used in visuals and to establish slicers.
- Fields slicers enable users to select specific fields to show.

## 08 Exercise - Configure a Semantic Model in Power BI

done.

## 09 Check your Knowledge

done.
