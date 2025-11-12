# n8n Workflow Examples

This directory contains example workflows to help you learn n8n.

## Example Workflows

### 1. Basic Examples
- **hello-world.json** - Simple manual trigger workflow
- **http-request.json** - Make HTTP requests to APIs
- **data-transformation.json** - Transform and manipulate data

### 2. Intermediate Examples
- **webhook-example.json** - Receive and process webhook data
- **scheduled-task.json** - Run workflows on a schedule
- **conditional-logic.json** - Use IF nodes for branching

### 3. Advanced Examples
- **error-handling.json** - Implement error workflows
- **sub-workflows.json** - Call workflows from other workflows
- **batch-processing.json** - Process large datasets efficiently

## How to Use

1. Download the JSON file
2. Open n8n
3. Click "Import from File"
4. Select the JSON file
5. Configure credentials if needed
6. Activate and test the workflow

## Workflow Descriptions

### Hello World
**File**: `hello-world.json`
**Purpose**: Introduction to n8n basics
**Nodes**: Manual Trigger → Set → Code

This workflow demonstrates:
- How to trigger a workflow manually
- Setting variables with the Set node
- Using the Code node for transformations

### HTTP Request Example
**File**: `http-request.json`
**Purpose**: Learn to make API calls
**Nodes**: Manual Trigger → HTTP Request → Set

This workflow demonstrates:
- Making GET requests to public APIs
- Parsing JSON responses
- Extracting specific fields from API responses

### Data Transformation
**File**: `data-transformation.json`
**Purpose**: Transform and filter data
**Nodes**: Manual Trigger → Code → Function → Set

This workflow demonstrates:
- Parsing complex JSON structures
- Filtering arrays
- Mapping and transforming data
- Using JavaScript in Function nodes

### Webhook Example
**File**: `webhook-example.json`
**Purpose**: Receive external data via webhook
**Nodes**: Webhook → Function → Respond to Webhook

This workflow demonstrates:
- Setting up webhook endpoints
- Validating incoming data
- Responding to webhook requests
- Security best practices

### Scheduled Task
**File**: `scheduled-task.json`
**Purpose**: Run automated tasks on schedule
**Nodes**: Cron → HTTP Request → IF → Email

This workflow demonstrates:
- Configuring cron schedules
- Fetching data periodically
- Conditional processing
- Sending notifications

### Conditional Logic
**File**: `conditional-logic.json`
**Purpose**: Implement decision-making in workflows
**Nodes**: Manual Trigger → IF → Set (multiple paths) → Merge

This workflow demonstrates:
- Using IF nodes for conditions
- Multiple execution paths
- Merging data from different branches
- Complex boolean logic

### Error Handling
**File**: `error-handling.json`
**Purpose**: Handle errors gracefully
**Nodes**: Manual Trigger → HTTP Request → Error Trigger → Slack/Email

This workflow demonstrates:
- Catching workflow errors
- Error notification systems
- Retry mechanisms
- Logging failed executions

### Sub-workflows
**File**: `sub-workflows.json`
**Purpose**: Modular workflow design
**Nodes**: Execute Workflow → Multiple sub-workflows

This workflow demonstrates:
- Calling other workflows
- Passing data between workflows
- Reusable workflow components
- Workflow organization

### Batch Processing
**File**: `batch-processing.json`
**Purpose**: Process large datasets efficiently
**Nodes**: Manual Trigger → Split In Batches → Process → Merge

This workflow demonstrates:
- Splitting large arrays into batches
- Processing items in groups
- Pagination patterns
- Performance optimization

## Creating Your Own Examples

When creating workflow examples:

1. **Keep it focused** - One concept per workflow
2. **Add annotations** - Use notes to explain nodes
3. **Use test data** - Pin sample data for testing
4. **Document** - Include descriptions and comments
5. **Export** - Save as JSON for sharing

## Example Workflow Template

```json
{
  "name": "Example Workflow Name",
  "nodes": [
    {
      "parameters": {},
      "name": "Node Name",
      "type": "n8n-nodes-base.nodeName",
      "position": [250, 300]
    }
  ],
  "connections": {},
  "active": false,
  "settings": {}
}
```

## Testing Examples

1. Import the workflow
2. Review the workflow description
3. Check node configurations
4. Review pinned test data
5. Execute manually
6. Review execution results
7. Modify and experiment

## Common Use Cases

### Data Sync
- Sync data between applications
- Keep databases in sync
- Update CRM records

### Notifications
- Send email alerts
- Slack notifications
- SMS messages
- Push notifications

### Data Processing
- ETL operations
- Data cleaning
- Format conversion
- Aggregation

### Integration
- Connect SaaS applications
- Automate repetitive tasks
- Build custom APIs
- Create webhooks

## Next Steps

1. Start with basic examples
2. Modify examples to fit your needs
3. Combine patterns from multiple examples
4. Create your own workflows
5. Share your workflows with the community

## Resources

- [n8n Workflow Templates](https://n8n.io/workflows)
- [n8n Community Workflows](https://community.n8n.io/c/workflows/)
- [n8n Documentation](https://docs.n8n.io/)
