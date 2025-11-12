# n8n Core Concepts

## Overview

Understanding these core concepts is essential for mastering n8n workflow automation.

## 1. Workflows

A workflow is a collection of nodes connected together to automate a process.

### Workflow Structure
- **Start Node**: Every workflow needs a trigger to start
- **Processing Nodes**: Transform, filter, or enrich data
- **End Nodes**: Final actions like sending data or storing results

### Workflow States
- **Active**: Running and listening for triggers
- **Inactive**: Saved but not executing
- **Executing**: Currently running

## 2. Nodes

Nodes are the building blocks of workflows.

### Node Types

#### Trigger Nodes
- **Manual Trigger**: Start workflow manually
- **Webhook**: HTTP endpoint to receive data
- **Cron**: Schedule-based execution
- **Email Trigger**: Start on email receipt
- **File Trigger**: Monitor file changes

#### Regular Nodes
- **HTTP Request**: Make API calls
- **Database Nodes**: Query databases (MySQL, PostgreSQL, MongoDB)
- **Transform Nodes**: Manipulate data (Set, Function, Code)
- **Integration Nodes**: Connect to services (Slack, Gmail, Notion)

#### Logic Nodes
- **IF**: Conditional branching
- **Switch**: Multiple conditions
- **Merge**: Combine data from multiple branches
- **Loop Over Items**: Iterate over arrays

## 3. Data Flow

### Understanding $json
- Each node receives and outputs data as JSON
- Access input data: `{{ $json.fieldName }}`
- Access all items: `{{ $items }}`

### Item Linking
- Data passes from one node to the next
- Each item maintains its structure
- Multiple items are processed sequentially

### Pinning Data
- Pin test data to nodes
- Useful for development and testing
- Persists across workflow edits

## 4. Expressions

### Basic Expressions
```javascript
// Access a field
{{ $json.name }}

// Mathematical operations
{{ $json.price * 1.1 }}

// String concatenation
{{ "Hello " + $json.name }}
```

### Advanced Expressions
```javascript
// Current date
{{ $now }}

// Previous node data
{{ $node["NodeName"].json }}

// Environment variables
{{ $env.API_KEY }}

// Workflow data
{{ $workflow.id }}
{{ $workflow.name }}
```

### Built-in Functions
```javascript
// Date formatting
{{ $now.toFormat('yyyy-MM-dd') }}

// String methods
{{ $json.email.toLowerCase() }}

// Array methods
{{ $json.items.length }}
{{ $json.items[0] }}
```

## 5. Credentials

### Credential Types
- **API Key**: Simple token-based auth
- **OAuth2**: Complex authorization flows
- **Username/Password**: Basic authentication
- **Custom**: User-defined credential types

### Best Practices
- Never hardcode credentials
- Use environment variables for sensitive data
- Rotate credentials regularly
- Limit credential scope

## 6. Error Handling

### Error Workflows
- Create dedicated error handling workflows
- Catch and process failed executions
- Send notifications on failures

### Error Triggers
- **Error Trigger Node**: Catches workflow errors
- Configure retry logic
- Log errors for debugging

### Debugging
- Use execution logs
- Enable verbose logging
- Test with pinned data
- Use breakpoints (Function nodes)

## 7. Variables and Parameters

### Workflow Variables
- Store reusable values
- Access across multiple nodes
- Update dynamically during execution

### Node Parameters
- Configure node behavior
- Use expressions for dynamic values
- Override with workflow variables

## 8. Execution Modes

### Main Mode
- Standard workflow execution
- Sequential processing
- Error stops workflow

### Try/Catch Mode
- Continue on errors
- Handle errors gracefully
- Conditional error paths

### Queue Mode
- Multiple simultaneous executions
- Manage concurrency
- Process large batches

## 9. Sub-workflows

### Workflow Calling
- Call one workflow from another
- Reuse common logic
- Modular design

### Benefits
- Maintainability
- Reusability
- Cleaner workflows

## 10. Webhooks

### Webhook Types
- **Production URL**: For active workflows
- **Test URL**: For development

### Webhook Methods
- GET: Retrieve data
- POST: Send data
- PUT: Update data
- DELETE: Remove data

### Security
- Use authentication headers
- Validate incoming data
- Rate limiting
- IP whitelisting

## Next Steps

1. Practice creating simple workflows
2. Experiment with expressions
3. Build error handling patterns
4. Explore integration nodes
5. Create reusable sub-workflows
