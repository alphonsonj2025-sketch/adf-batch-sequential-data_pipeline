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
