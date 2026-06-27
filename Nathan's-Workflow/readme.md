# n8n Order Processing Automation Workflow

## Overview

This project demonstrates an end-to-end order processing automation workflow built using **n8n**. The workflow retrieves order data from a data warehouse, processes it based on order status, stores records for follow-up, sends team notifications, and runs automatically on a weekly schedule. 
## Workflow Features

### 1. Retrieve Order Data

* Connects to the data warehouse.
* Fetches relevant order information including:

  * Order ID
  * Order Status
  * Order Value
  * Employee Name

### 2. Filter Orders

* Separates orders based on their status:

  * **Processing**
  * **Booked**

### 3. Calculate Booked Order Value

* Counts the total number of booked orders.
* Calculates the combined value of all booked orders using an n8n Code node.

### 4. Notify the Team

* Sends a summary of booked orders to the company's Discord channel.
* Keeps team members informed automatically without manual reporting.

### 5. Store Processing Orders

* Extracts details of orders that are still in the **Processing** state.
* Inserts them into an n8n Data Table for future follow-up and tracking.

### 6. Schedule Automation

* Uses a Schedule Trigger node.
* Runs automatically every **Monday morning**, ensuring weekly order reports are generated without manual intervention.

## Technologies Used

* n8n
* JavaScript / Python (Code Node)
* Discord Integration
* n8n Data Tables
* Conditional Filtering
* Scheduled Workflow Automation

## Workflow Summary

Data Warehouse → Filter Orders → Calculate Booked Orders → Send Discord Notification → Store Processing Orders in Data Table → Run Automatically Every Monday

## Learning Outcomes

Through this project, I learned how to:

* Build multi-node workflows in n8n.
* Integrate external services like Discord.
* Use Data Tables for internal data storage.
* Process and filter data using Code nodes.
* Perform aggregations and calculations.
* Automate recurring workflows with scheduled triggers.
* Design end-to-end business process automations with minimal manual effort.
