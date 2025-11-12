# n8n Glossary

Quick reference guide for n8n terminology and concepts.

## A

**Active Workflow**
A workflow that is turned on and will execute when triggered. Indicated by a green toggle in the workflow editor.

**API (Application Programming Interface)**
A way for different software applications to communicate with each other. n8n uses APIs to connect to various services.

**Authentication**
The process of verifying identity when connecting to external services. n8n supports various authentication methods including API keys, OAuth2, and basic auth.

## B

**Batch Processing**
Processing multiple items in groups rather than one at a time, improving performance for large datasets.

**Binary Data**
Non-text data such as images, PDFs, or other files that can be passed between nodes in n8n.

## C

**Credentials**
Stored authentication information (API keys, passwords, tokens) used to connect to external services securely.

**Cron**
A time-based job scheduler. In n8n, the Cron node allows you to run workflows on a schedule using cron expressions.

**Code Node**
A node that allows you to write custom JavaScript code to process data within your workflow.

## D

**Data Pinning**
Saving sample data to a node for testing purposes. Pinned data persists across workflow edits.

**Drag and Drop**
The method of adding and connecting nodes in the n8n workflow editor by dragging them onto the canvas.

## E

**Error Trigger**
A special trigger node that executes when another workflow encounters an error, allowing you to build error handling workflows.

**Error Workflow**
A dedicated workflow that handles errors from other workflows, typically used for logging or notifications.

**Execution**
A single run of a workflow. Each execution has a unique ID and can be viewed in the execution history.

**Expression**
Code enclosed in `{{ }}` that allows you to access and manipulate data dynamically in node parameters.

## F

**Function Node**
A node that allows you to write JavaScript functions to transform data. Similar to Code node but uses a different syntax.

**Fair-code**
n8n's licensing model that is more open than traditional proprietary software but with some restrictions on usage.

## G

**GET Request**
An HTTP method used to retrieve data from an API endpoint.

## H

**HTTP Request Node**
A versatile node for making API calls to external services using various HTTP methods.

**Headless**
Running n8n without a graphical user interface, typically for server deployments.

## I

**IF Node**
A conditional node that routes data to different paths based on whether a condition is true or false.

**Inactive Workflow**
A saved workflow that is not currently executing. Must be activated to run automatically.

**Integration**
A pre-built connection to a specific service (e.g., Slack, Gmail, Notion). n8n has 400+ integrations.

**Item**
A single piece of data (JSON object) that flows through a workflow. Workflows can process multiple items.

## J

**JSON (JavaScript Object Notation)**
The data format used by n8n to pass information between nodes.

**$json**
The expression variable that accesses the JSON data from the current item.

## L

**Loop Over Items**
A node that processes an array of items one at a time, useful for operations that can't handle multiple items.

## M

**Manual Trigger**
A trigger node that starts a workflow when you manually click the execute button. Useful for testing.

**Merge Node**
A node that combines data from multiple workflow branches into a single output.

## N

**Node**
A building block of a workflow that performs a specific action, such as fetching data, transforming it, or sending it somewhere.

**n8n**
The name of the workflow automation platform. It stands for "nodemation" (node automation).

## O

**OAuth2**
An authorization framework that allows n8n to access external services on your behalf without exposing your password.

## P

**POST Request**
An HTTP method used to send data to an API endpoint.

**Production URL**
The permanent webhook URL used when a workflow is active in production.

## Q

**Queue Mode**
An execution mode that allows multiple workflow runs to be queued and processed sequentially or in parallel.

## R

**Regular Node**
Any node that is not a trigger. Regular nodes process data but don't start workflows.

**Retry**
Automatically attempting to execute a failed node again. Can be configured per node.

## S

**Self-hosted**
Running n8n on your own server or infrastructure rather than using n8n.cloud.

**Set Node**
A node used to add, modify, or remove fields from your data.

**Split In Batches**
A node that divides an array of items into smaller groups for batch processing.

**Sub-workflow**
A workflow that is called by another workflow, allowing for modular and reusable workflow design.

**Switch Node**
A node that routes data to different paths based on multiple conditions, like a multi-way IF statement.

## T

**Test URL**
A temporary webhook URL used for testing workflows before activation.

**Trigger Node**
A node that starts a workflow execution, such as Webhook, Cron, or Manual Trigger.

## V

**Variable**
A named value that can be used throughout a workflow, accessed using expressions.

**Version Control**
The practice of tracking and managing changes to workflows over time.

## W

**Webhook**
An HTTP endpoint that receives data from external services to trigger or provide data to workflows.

**Webhook Trigger**
A trigger node that creates an HTTP endpoint to receive data from external services.

**Workflow**
A collection of connected nodes that automate a process from start to finish.

## Expression Variables

**$binary**
Access binary data (files, images) from the current item.

**$env**
Access environment variables configured in n8n.

**$execution**
Information about the current workflow execution (ID, mode, etc.).

**$input**
Reference to the input data in Code nodes.

**$item**
Access the current item being processed, including its index.

**$items**
Access all items being processed in the current execution.

**$json**
Access the JSON data from the current item.

**$node**
Access data from a specific node by name.

**$now**
The current date and time as a Luxon DateTime object.

**$parameter**
Access parameter values within the current node.

**$prevNode**
Information about the previous node in the workflow.

**$runIndex**
The index of the current run in a loop.

**$today**
The current date at midnight as a Luxon DateTime object.

**$workflow**
Information about the current workflow (name, ID, active status).

## Common Abbreviations

- **API**: Application Programming Interface
- **CRUD**: Create, Read, Update, Delete
- **CSV**: Comma-Separated Values
- **ETL**: Extract, Transform, Load
- **GUI**: Graphical User Interface
- **HTTP**: Hypertext Transfer Protocol
- **JSON**: JavaScript Object Notation
- **REST**: Representational State Transfer
- **SQL**: Structured Query Language
- **URL**: Uniform Resource Locator
- **UUID**: Universally Unique Identifier
- **XML**: Extensible Markup Language

## Tips

- Hover over any term in the n8n UI to see its definition
- Use the search function (Ctrl+F / Cmd+F) in this document
- Refer to official n8n documentation for detailed explanations
- Join the n8n community for help with terminology
