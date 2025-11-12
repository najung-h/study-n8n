# n8n Study Repository

LifeHack - no-code automation journey with n8n

## 📚 About n8n

n8n is a fair-code licensed workflow automation tool. It enables you to connect anything to everything via its open, fair-code model. n8n can be self-hosted, easily extended, and used with internal tools.

## 🎯 Learning Objectives

This repository is designed to help you master n8n through:
- Understanding core concepts
- Hands-on workflow examples
- Best practices
- Advanced patterns and techniques

## 📖 Table of Contents

1. [Getting Started](#getting-started)
2. [Core Concepts](#core-concepts)
3. [Workflow Examples](#workflow-examples)
4. [Best Practices](#best-practices)
5. [Resources](#resources)

## 🚀 Getting Started

### Installation Options

1. **Docker** (Recommended for beginners)
   ```bash
   docker run -it --rm --name n8n -p 5678:5678 n8nio/n8n
   ```

2. **npm**
   ```bash
   npm install n8n -g
   n8n
   ```

3. **n8n.cloud** - Use the hosted version at https://n8n.cloud

### First Workflow

1. Access n8n at `http://localhost:5678`
2. Create a new workflow
3. Add a trigger node (e.g., Manual Trigger)
4. Add an action node (e.g., HTTP Request)
5. Execute the workflow

## 🧠 Core Concepts

### Nodes
- **Trigger Nodes**: Start workflows (Webhook, Cron, Manual)
- **Action Nodes**: Perform operations (HTTP Request, Database, Transform)
- **Logic Nodes**: Control flow (IF, Switch, Merge)

### Expressions
- Access data using `{{ $json.fieldName }}`
- Use JavaScript with `{{ $item.json.fieldName }}`
- Perform calculations and transformations

### Credentials
- Securely store API keys and passwords
- Reuse across multiple workflows
- Support for OAuth2

### Executions
- View execution history
- Debug failed workflows
- Retry executions

## 💡 Workflow Examples

### Example 1: Simple HTTP Request
- Trigger: Manual
- Action: HTTP Request to public API
- Output: Display JSON response

### Example 2: Data Transformation
- Trigger: Webhook
- Transform: Parse and filter data
- Action: Send to another service

### Example 3: Scheduled Task
- Trigger: Cron
- Fetch: Get data from database
- Process: Transform and validate
- Send: Email notification

## ✅ Best Practices

1. **Naming Conventions**
   - Use descriptive workflow names
   - Label nodes clearly
   - Comment complex logic

2. **Error Handling**
   - Add error workflows
   - Use try-catch patterns
   - Log failures

3. **Performance**
   - Batch operations when possible
   - Use pagination for large datasets
   - Optimize node execution order

4. **Security**
   - Use credentials instead of hardcoded keys
   - Validate webhook inputs
   - Limit exposed endpoints

## 📚 Resources

### Official Documentation
- [n8n Documentation](https://docs.n8n.io/)
- [n8n Community](https://community.n8n.io/)
- [n8n GitHub](https://github.com/n8n-io/n8n)

### Learning Materials
- [n8n Academy](https://docs.n8n.io/courses/)
- [Workflow Templates](https://n8n.io/workflows)
- [YouTube Tutorials](https://www.youtube.com/c/n8n-io)

### Advanced Topics
- Custom Nodes Development
- Self-hosting Configuration
- Scaling n8n
- API Integration Patterns

## 🤝 Contributing

Feel free to add your own workflow examples, notes, and learnings to this repository.

## 📝 License

This study repository is for educational purposes.
