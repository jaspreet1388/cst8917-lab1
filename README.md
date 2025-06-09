## Azure Functions with Storage Queue and Azure SQL Output Bindings
This project demonstrates the use of Azure Functions with Storage Queue and Azure SQL output bindings using Python and Visual Studio Code.

## Overview
This project includes:

A function that adds messages to an Azure Storage Queue.
A function that inserts records into an Azure SQL Database.
Both functions were created and tested locally before being deployed to Azure.

## Prerequisites
Python 3.10+
Azure Functions Core Tools
Visual Studio Code with Azure Functions and Python extensions
Azure CLI
An active Azure subscription
Setup Instructions
Storage Queue Function
Create a Storage Account on Azure.
Set up a Queue named outqueue.
Update local.settings.json with your storage connection string:
{
  "Values": {
    "AzureWebJobsStorage": "<Your_Storage_Connection_String>"
  }
}
Run the function locally or deploy to Azure.
Azure SQL Function
Create an Azure SQL Database and SQL Server.

Create a table using the following schema:

CREATE TABLE dbo.ToDo (
 [Id] UNIQUEIDENTIFIER PRIMARY KEY,
 [order] INT NULL,
 [title] NVARCHAR(200) NOT NULL,
 [url] NVARCHAR(200) NOT NULL,
 [completed] BIT NOT NULL
);
Update local.settings.json with your SQL connection string:

{
  "Values": {
    "SqlConnectionString": "<Your_SQL_Connection_String>"
  }
}
Running Locally
Navigate to the project root through VS code:
Install dependencies:
pip install -r requirements.txt
Start the function app locally:
func start
Testing
Trigger the Storage Queue function via an HTTP request
Verify that a message is added to the storage queue.
Trigger the Azure SQL function similarly and confirm a new record is inserted into the database.
Important
The function_app.py code has been updated from Storage Queue output binding to Azure SQL Database output binding.
