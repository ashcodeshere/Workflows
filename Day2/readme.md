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



**subregion**, producing a clean dataset that can be reused in reporting, analytics, and downstream workflows such as sales reporting.
