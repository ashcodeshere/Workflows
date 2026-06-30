# n8n Foundations Workflows

This repository contains my completed workflows from the **n8n Foundations (N8N101)** course. Each section focuses on different automation concepts, gradually building from basic API communication to a complete data processing pipeline.

---

# Section 1 – Academy Registration

## Overview

This module introduces the fundamentals of building workflows in **n8n**. The workflow registers an n8n instance with the Academy training system by sending authenticated API requests. It also establishes best practices such as workflow organization, node naming, and secure authentication.

---

## What Was Built

The workflow includes the following tasks:

- Created a new workflow following the required naming convention
- Added workflow tags for organization
- Configured a Manual Trigger to start the workflow
- Created and used Header Authentication credentials
- Connected to the Academy registration API
- Sent workflow information through query parameters
- Executed the workflow manually
- Verified the registration response from the API
- Documented the workflow using Sticky Notes (optional best practice)

---

## Concepts Learned

During this module, the following n8n concepts and features were practiced:

- Creating workflows from scratch
- Navigating the node panel
- Connecting nodes correctly
- Configuring HTTP Request nodes
- Creating reusable credentials
- Using Header Authentication
- Sending query parameters
- Executing workflows manually
- Reading API responses
- Organizing workflows with names and tags
- Following consistent node naming conventions
- Documenting workflows with Sticky Notes

---

## Workflow Outcome

By the end of this section, the workflow is capable of:

- Registering an n8n instance with the Academy
- Authenticating API requests securely
- Sending workflow metadata
- Receiving and validating registration confirmation

---

## Skills Gained

- Workflow creation
- HTTP API integration
- Authentication with credentials
- Query parameter configuration
- Manual workflow execution
- Workflow documentation
- Basic automation best practices

---

# Section 2 – Sales Data Pipeline

## Overview

This module focuses on building a complete sales data pipeline in **n8n**. The workflow retrieves sales data from an API, transforms and processes it, performs analysis on delivered orders, generates summary reports, and exports the results as a CSV file. Throughout the module, the workflow is expanded using branching to support multiple business use cases from a single data source.

---

## What Was Built

The workflow includes the following stages:

- Connected to a secured sales data API using Header Authentication
- Retrieved sales records from the warehouse
- Split the orders array into individual workflow items
- Calculated the total value for each order
- Aggregated transformed orders and sent them for processing
- Created parallel workflow branches for different business requirements
- Filtered only delivered orders
- Generated regional sales summaries
- Renamed summary fields for better readability
- Aggregated regional analysis and submitted it for validation
- Added report metadata
- Converted summarized data into a CSV report
- Uploaded the generated report to complete the pipeline

---

## Concepts Learned

During this module, the following n8n concepts and features were practiced:

- Using Header Authentication with APIs
- Working with nested JSON responses
- Splitting arrays into individual items using **Split Out**
- Creating calculated fields with expressions
- Using **Edit Fields (Set)** to reshape data
- Aggregating multiple items into a single payload
- Building branching workflows
- Filtering data using **IF** nodes
- Summarizing data with aggregation functions (Sum, Count, Average)
- Renaming fields for cleaner output
- Adding dynamic metadata using expressions
- Converting JSON data into CSV files
- Working with binary files in n8n
- Uploading binary files through HTTP Request nodes
- Designing an end-to-end ETL (Extract, Transform, Load) workflow

---

## Workflow Outcome

By the end of this section, the workflow is capable of:

- Securely retrieving sales data
- Processing and transforming order information
- Producing business-ready regional analysis
- Generating downloadable CSV reports
- Sending processed data and reports to external endpoints
- Demonstrating a complete ETL-style workflow in n8n

---

## Skills Gained

- API integration
- Data transformation
- Data filtering
- Aggregation and summarization
- Workflow branching
- Report generation
- CSV file creation
- Binary file handling
- End-to-end workflow automation
```
