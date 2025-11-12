# Getting Started with n8n

This guide will help you get started with n8n and complete your first workflow.

## Prerequisites

- Basic understanding of APIs and workflows
- Computer with internet connection
- (Optional) Docker installed for local setup

## Installation

### Option 1: Try n8n Cloud (Easiest)

1. Visit [n8n.cloud](https://n8n.cloud)
2. Sign up for a free account
3. Start creating workflows immediately

### Option 2: Docker (Recommended for Learning)

```bash
docker run -it --rm \
  --name n8n \
  -p 5678:5678 \
  -v ~/.n8n:/home/node/.n8n \
  n8nio/n8n
```

Access n8n at: `http://localhost:5678`

### Option 3: npm

```bash
npm install n8n -g
n8n
```

Access n8n at: `http://localhost:5678`

## Your First Workflow

### Step 1: Create a New Workflow

1. Open n8n in your browser
2. Click "New Workflow" or the "+" button
3. You'll see an empty canvas

### Step 2: Add a Trigger

1. Click the "+" button on the canvas
2. Search for "Manual Trigger"
3. Click to add it to your workflow
4. This node will start your workflow when you click "Execute"

### Step 3: Add an HTTP Request Node

1. Click the "+" button to the right of the Manual Trigger
2. Search for "HTTP Request"
3. Click to add it
4. Configure the node:
   - URL: `https://jsonplaceholder.typicode.com/users/1`
   - Method: GET
5. Click "Execute Node" to test

### Step 4: Add a Set Node

1. Click the "+" button after HTTP Request
2. Search for "Set"
3. Add it to your workflow
4. Configure to extract fields:
   - Add String value: `name` = `{{ $json.name }}`
   - Add String value: `email` = `{{ $json.email }}`
5. Click "Execute Node" to test

### Step 5: Save and Execute

1. Click the "Save" button (top right)
2. Name your workflow: "My First Workflow"
3. Click "Execute Workflow"
4. View the results in each node

Congratulations! You've created your first n8n workflow! 🎉

## Understanding What Happened

1. **Manual Trigger** - Started the workflow when you clicked execute
2. **HTTP Request** - Made a GET request to a public API
3. **Set Node** - Extracted specific fields from the API response

## Next Steps

### Learn Core Concepts

1. **Nodes**: Building blocks of workflows
   - Read: [Core Concepts](./docs/core-concepts.md)

2. **Expressions**: Access and transform data
   - Try: `{{ $json.fieldName }}`
   - Practice: Modify the Set node expressions

3. **Connections**: Link nodes together
   - Experiment: Add more nodes to your workflow

### Try More Examples

Import the example workflows from the `examples/` directory:

1. **hello-world.json** - Basic workflow structure
2. **http-request.json** - Advanced API calls
3. More examples in `examples/README.md`

### Common Tasks

#### Import a Workflow

1. Download a `.json` workflow file
2. In n8n, click "Import from File"
3. Select the file
4. Review and execute

#### Export a Workflow

1. Open your workflow
2. Click the menu (three dots)
3. Select "Download"
4. Save the `.json` file

#### Activate a Workflow

1. Save your workflow
2. Toggle the "Active" switch (top right)
3. Workflows with triggers will now run automatically

## Building Real Workflows

### Example: Automated Data Sync

**Goal**: Sync data from one system to another daily

**Nodes**:
1. Cron Trigger - Run daily at 9 AM
2. HTTP Request - Fetch data from source
3. Function - Transform data
4. HTTP Request - Send to destination
5. Email - Send success notification

### Example: Webhook Processor

**Goal**: Receive and process webhook data

**Nodes**:
1. Webhook Trigger - Receive POST requests
2. Code - Validate incoming data
3. IF - Check conditions
4. Multiple paths based on conditions
5. Respond to Webhook - Send response

### Example: Error Handling

**Goal**: Handle failures gracefully

**Nodes**:
1. Main workflow with potential failures
2. Error Trigger - Catches errors
3. Set - Format error details
4. Slack/Email - Notify about errors

## Tips for Success

### 1. Start Small
- Begin with simple workflows
- Add complexity gradually
- Test each node individually

### 2. Use Test Data
- Pin data to nodes for testing
- Test before activating
- Use Manual Trigger for development

### 3. Read the Docs
- Each node has documentation
- Click the "?" icon in nodes
- Review examples in the docs

### 4. Join the Community
- [n8n Community Forum](https://community.n8n.io/)
- [n8n Discord](https://discord.gg/n8n)
- [GitHub Discussions](https://github.com/n8n-io/n8n/discussions)

### 5. Practice Expressions
```javascript
// Access data
{{ $json.name }}

// Current date
{{ $now.toFormat('yyyy-MM-dd') }}

// Previous node data
{{ $node["NodeName"].json }}

// Conditional value
{{ $json.status === 'active' ? 'Yes' : 'No' }}
```

## Troubleshooting

### Workflow Won't Execute
- Check if all required fields are filled
- Verify credentials are configured
- Check for red exclamation marks on nodes

### No Data in Nodes
- Execute previous nodes first
- Check connections between nodes
- Verify the trigger is firing

### Expression Errors
- Check syntax: `{{ expression }}`
- Verify field names match data structure
- Use the Expression Editor for help

### API Errors
- Check API endpoint URL
- Verify authentication credentials
- Review API documentation
- Check rate limits

## Resources

### Documentation
- [n8n Official Docs](https://docs.n8n.io/)
- [n8n Courses](https://docs.n8n.io/courses/)
- [API Documentation](https://docs.n8n.io/api/)

### Learning Materials
- [Core Concepts](./docs/core-concepts.md)
- [Best Practices](./docs/best-practices.md)
- [Workflow Examples](./examples/README.md)

### Community
- [Community Forum](https://community.n8n.io/)
- [Workflow Templates](https://n8n.io/workflows)
- [YouTube Channel](https://www.youtube.com/c/n8n-io)

## What's Next?

1. ✅ Complete your first workflow
2. ⬜ Import and study example workflows
3. ⬜ Read core concepts documentation
4. ⬜ Build a workflow for your own use case
5. ⬜ Learn about credentials and security
6. ⬜ Explore integrations with your tools
7. ⬜ Join the n8n community
8. ⬜ Share your first workflow!

Happy automating! 🚀
