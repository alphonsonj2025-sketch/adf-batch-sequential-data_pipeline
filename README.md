# adf-batch-sequential-data-pipeline
Azure Data Factory pipeline demonstrating batch ingestion and sequential data loading using dynamic table processing, ForEach activity, and controlled execution.
![Linked Service](images/01_linked_service.png)

Batch & Sequential Processing Design
This pipeline was enhanced to support dynamic batch ingestion using parameterization and controlled execution.
⚙️ Key Features
Batch Processing: Multiple tables processed in one pipeline
Sequential Execution: Controlled using ForEach (Batch count = 1)
Dynamic Table Handling: Table names passed as parameters

[
  {"table": "SalesLT.Customer", "folder": "customer"},
  {"table": "SalesLT.Product", "folder": "product"},
  {"table": "SalesLT.SalesOrderHeader", "folder": "salesorder"}
]

ForEach Loop
   ↓
Dynamic Copy Activity
   ↓
SQL → Data Lake (per table)

🔗 Linked Service – Azure SQL Database


We created a secure connection between Azure Data Factory and Azure SQL Database.

Configuration:

- Server: vsqlserversolavise237.database.windows.net
- Database: vsqlsolavise237
- Authentication: SQL Authentication

Result:
Connection tested successfully ✅
<br>
![SQL Linked Service](images/03_sql_linked_services_success.png)
