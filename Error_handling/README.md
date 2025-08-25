This section depicts error handling and logging in SSIS.

Create a table to store the error log using an SQL task transformation
![Alt text](create_log_table.png)
Place a SQL task transformation on the Event Handlers table with the following config
![Alt text](error_handling1.png)
![Alt text](error_handling2.png)
The expression builder for the SQL task transformation on the event handlers tab
![Alt text](expression_builder.png)
To enable SQL logging, right click on the dataflow canvas and configure SQL logging as depicted below
![Alt text](SQL_logging1.png)
![Alt text](SQL_logging2.png)
To enable file logging, right click on the dataflow canvas and configure file logging as depicted below
![Alt text](file_logging1.png)
The control flow
![Alt text](control_flow.png)
The dataflow
![Alt text](dataflow.png)
