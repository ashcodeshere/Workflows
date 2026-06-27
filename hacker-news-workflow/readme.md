# First n8n Workflow – Hacker News Articles

## Overview

This project is my first workflow built using **n8n**, designed to introduce the fundamentals of workflow automation. The workflow retrieves the latest Hacker News articles related to **automation**, demonstrating how to configure nodes, execute workflows, inspect outputs, and manage workflow settings.

## Workflow Steps

### 1. Manual Trigger

The workflow begins with a **Manual Trigger** node, allowing it to be executed on demand by clicking the **Execute Workflow** button. This is useful for testing and learning before using automated triggers such as schedules or webhooks.

### 2. Hacker News Node

A **Hacker News** node is connected to the trigger to fetch articles from Hacker News.

The node is configured with the following parameters:

* **Resource:** All
* **Operation:** Get Many
* **Limit:** 50 articles
* **Keyword Filter:** automation

This configuration retrieves the ten most recent Hacker News articles containing the keyword **"automation."**

### 3. Node Settings

To improve workflow readability, the node includes:

* A descriptive note explaining its purpose.
* Display of the note directly on the workflow canvas.
* A meaningful node name for easier identification in larger workflows.

### 4. Execute and Verify

The node is executed to retrieve data successfully. The output is inspected using:

* **Table View** for structured records
* **JSON View** for raw data
* **Schema View** to understand the data structure

The execution details, including execution time, start time, and returned item count, help verify that the workflow is functioning correctly.

### 5. Save the Workflow

The workflow is renamed to **Hacker News Workflow** and saved, following best practices for organizing and maintaining automation projects.

## Technologies Used

* n8n
* Manual Trigger
* Hacker News Integration
* Workflow Configuration
* JSON Data Inspection

## Learning Outcomes

Through this project, I learned how to:

* Create and connect nodes in n8n.
* Configure node parameters and settings.
* Retrieve data from an external service.
* Execute individual nodes and entire workflows.
* Inspect workflow output using Table, JSON, and Schema views.
* Understand node execution status and debugging information.
* Save, rename, and organize workflows using n8n best practices.

## Workflow Overview

Manual Trigger → Hacker News (Get 50 Latest Articles with Keyword "automation") → Display Results
