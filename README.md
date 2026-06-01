📊 Data Modeler – Power BI Data Modeling Project

Project Overview

This project focuses on designing and implementing a normalized data model in Power BI using multiple fact and dimension tables. The objective is to demonstrate data modeling concepts including relationships, cardinality, schema design, hierarchies, and filter flow management.

Objective

Build a well-structured relational data model in Power BI by:

- Creating relationships between fact and dimension tables
- Implementing a Star Schema design
- Managing active and inactive relationships
- Configuring cardinality and cross-filter directions
- Creating business hierarchies
- Verifying relationship behavior using Matrix visuals

Dataset Structure

Fact Tables

Sales_Fact

- SalesID
- CustomerID
- ProductID
- RegionID
- DateKey
- Quantity
- Revenue
- Discount

Returns_Fact

- ReturnID
- SalesID
- ReturnDateKey
- Reason

Dimension Tables

Customer_Dim

- CustomerID
- FullName
- Age
- Gender
- Segment

Product_Dim

- ProductID
- ProductName
- Category
- Subcategory
- Brand

Region_Dim

- RegionID
- Country
- State
- City

Date_Dim

- DateKey
- Date
- Month
- Quarter
- Year
- Fiscal Year

Data Preparation

Performed in Power Query:

- Imported all source files
- Verified data types
- Removed blank rows
- Validated key columns
- Loaded cleaned tables into the data model

Data Model Design

Star Schema

Sales_Fact acts as the central fact table connected to:

- Customer_Dim
- Product_Dim
- Region_Dim
- Date_Dim

Returns Model

Returns_Fact is connected to:

- Sales_Fact (via SalesID)
- Date_Dim (via ReturnDateKey as inactive relationship)

Relationships

From Table| To Table| Cardinality
Customer_Dim| Sales_Fact| 1 : Many
Product_Dim| Sales_Fact| 1 : Many
Region_Dim| Sales_Fact| 1 : Many
Date_Dim| Sales_Fact| 1 : Many
Sales_Fact| Returns_Fact| 1 : Many
Date_Dim| Returns_Fact| 1 : Many (Inactive)

Hierarchies Created

Date Hierarchy

Year → Quarter → Month → Date

Region Hierarchy

Country → State → City

Product Hierarchy

Category → Subcategory → ProductName

Verification

Matrix visual used to validate:

- Revenue by Customer Segment
- Sales by Product Category and Region
- Return Reasons by Fiscal Year

Key Learnings

- Star Schema Design
- Fact & Dimension Modeling
- Relationship Management
- Cardinality Configuration
- Filter Flow Optimization
- Inactive Relationship Handling
- Hierarchy Creation in Power BI

Tools Used

- Microsoft Power BI Desktop
- Power Query
- Data Modeling View

Project Outcome

Successfully developed a scalable and normalized Power BI data model with optimized relationships, business hierarchies, and validation matrices to ensure accurate analytical reporting.
