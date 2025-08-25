This section functions on loading a DWH fact table

Code for staging table

```
CREATE TABLE [Fact].[Orders_update](
	[CustomerSK] [int] NULL,
	[EmployeeSK] [int] NULL,
	[ProductSK] [int] NULL,
	[DateSK] int NULL,
	[OrderId] [int] NULL,
	[Quantity] [int] NULL,
	[UnitPrice] [decimal](18, 0) NULL,
	[TaxRate] [decimal](18, 0) NULL,
	[LastEditedWhen] [datetime2](7) NULL
) ON [PRIMARY]
GO
```

Control flow Steps/Transformations:

Staging Table creation
![Alt text](staging_table.png)
Migrate data to fact table (Data flow task)

Update Fact table from staging table
![Alt text](update_fact_table.png)

DataFlow Steps/Transformations:

Source connection
![Alt text](ole_db_source.png)
Customer lookup
![Alt text](customer_lookup1.png)
![Alt text](customer_lookup2.png)
Customer Derived column (missing surrogate key)
![Alt text](customer_derived_column.png)
Employee Derived column (missing surrogate key)
![Alt text](employee_derived_column.png)
Product lookup
![Alt text](product_lookup1.png)
![Alt text](product_lookup2.png)
Product Derived column (missing surrogate key)
![Alt text](product_derived_column.png)
Date lookup
![Alt text](date_lookup1.png)
![Alt text](date_lookup2.png)
Date Derived column (missing surrogate key)
![Alt text](date_derived_column.png)
Fact table lookup
![Alt text](fact_lookup1.png)
![Alt text](fact_lookup2.png)
Fact orders Ole Odb destination
![Alt text](fact_orders_ole_dest.png)
Conditional Split
![Alt text](conditional_split.png)
Staging Fact orders Ole Odb destination
![Alt text](staging_table_load.png)

Control Flow
![Alt text](control_flow.png)
Dataflow
![Alt text](dataflow1.png)
![Alt text](dataflow2.png)
![Alt text](dataflow3.png)

Source data:
orders table
![Alt text](orders_table.png)
Dimension Tables:
Customers
![Alt text](dim_customers.png)
Dates
![Alt text](dim_date.png)
Products
![Alt text](dim_products.png)
Fact Tables
Fact orders table
![Alt text](fact_orders.png)
