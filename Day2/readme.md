# 📘 n8n Learning Notes

This repository contains my n8n learning workflows and exercises. The JSON files represent the workflows I built while learning different n8n concepts, core nodes, data handling, and automation techniques.

## 🚀 What I Learned

### 📦 n8n Data Structure

* Understood how n8n stores data using the `json` object.
* Learned how to create custom datasets using the **Code** node.
* Worked with nested JSON objects.
* Created arrays of objects for workflow testing and simulations.

### 💻 Code Node

* Wrote JavaScript inside the Code node.
* Created and modified workflow data programmatically.
* Used `$input.all()` to access incoming items.
* Added new fields to existing data.
* Returned data in the format expected by n8n.

### 🔗 Referencing Data

* Referenced data from previous nodes using expressions.
* Learned the difference between:

  * `.first()`
  * `.last()`
  * `.all()`
  * `.item`
* Referenced data from non-connected nodes using the `$()` syntax.
* Understood the importance of meaningful node names for easier workflow maintenance.

### 🌐 HTML & XML Processing

* Used the **HTML** node to extract information from web pages using CSS selectors.
* Converted JSON to XML and XML to JSON using the **XML** node.
* Worked with data returned from external APIs.

### 📅 Date & Time

* Learned different date and time formats supported by n8n.
* Used the **Date & Time** node to:

  * Round dates
  * Add and subtract time
  * Compare dates
  * Format date values
* Used **Luxon expressions** for advanced date calculations.
* Learned how to pause workflow execution using the **Wait** node.

### 📁 Binary Data

* Learned how n8n handles binary files such as images, PDFs, audio, and videos.
* Downloaded files using the **HTTP Request** node.
* Edited images using the **Edit Image** node.
* Converted JSON data into downloadable CSV files using the **Convert to File** node.
* Learned about extracting structured data from binary files.

## 🛠️ Core Nodes Covered

* Manual Trigger
* Code
* HTTP Request
* Edit Fields (Set)
* HTML
* XML
* Date & Time
* If
* Wait
* Convert to File
* Extract From File
* Edit Image

## 📚 Skills Gained

* Building and organizing n8n workflows
* Creating and manipulating JSON data
* Writing JavaScript inside n8n
* Working with expressions
* Referencing data across nodes
* Processing HTML and XML
* Handling date and time operations
* Working with binary files
* Calling external APIs
* Converting data between different formats
* Following best practices for workflow and node naming

## 📂 Repository Contents

This repository contains the workflow JSON files created while learning the above concepts. Each workflow demonstrates a specific feature or node in n8n and serves as a reference for future automation projects.

---

**Purpose:** Document my learning journey with n8n and maintain a collection of reusable workflow examples for future reference.





# 📘 Customer Data Enrichment

This workflow enriches customer records by merging customer information from an n8n Data Table with country information retrieved from an external API. It automatically fills in missing **region** and **subregion** fields, creating a complete customer dataset for reporting and analytics.

## 🎯 Objective

The goal of this workflow is to:

* Retrieve customer records from a Data Table.
* Fetch country metadata from an external API.
* Merge both datasets using the customer's country.
* Populate missing geographic information.
* Update the Data Table with enriched customer records.

## 🚀 What I Learned

### Data Tables

* Creating Data Tables from CSV files.
* Reading all rows from a Data Table.
* Updating existing rows using conditions.
* Mapping individual columns during updates.

### Merge Node

* Using **Merge by Fields** to combine data from two different sources.
* Matching records using common fields (`customerCountry` and `name`).
* Enriching existing records without modifying the original structure.

### HTTP Request

* Fetching country information from an external API.
* Working with JSON responses.
* Using API data to enhance internal datasets.

### Parallel Execution

* Running multiple branches simultaneously from a Manual Trigger.
* Combining outputs from independent nodes into a single workflow.

### Data Mapping

* Updating only selected columns instead of replacing entire records.
* Preserving existing customer information while adding new values.

### Best Practices

* Using meaningful node names for readability.
* Keeping workflows modular for reuse in later automation tasks.
* Preparing clean datasets before generating reports.

## 🛠️ Nodes Used

* Manual Trigger
* Data Table (Get Rows)
* HTTP Request
* Merge
* Data Table (Update Rows)

## 🔄 Workflow Overview

```text
Manual Trigger
      │
 ┌────┴─────┐
 │          │
GetCustomers  GetCountries
      │          │
      └────Merge────┘
            │
    UpdateCustomers
```

## 📚 Key Concepts Practiced

* Data enrichment
* Dataset merging
* Field-based joins
* Data Table operations
* API integration
* Updating records dynamically
* Geographic data mapping

## 📌 Outcome

After execution, every customer record is enriched with its corresponding **region** and **subregion**, producing a clean dataset that can be reused in reporting, analytics, and downstream workflows such as sales reporting.
