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
2. [Learning Path](./docs/learning-path.md) - Structured guide from beginner to expert
3. [Core Concepts](#core-concepts)
4. [Workflow Examples](#workflow-examples)
5. [Best Practices](#best-practices)
6. [Resources](#resources)

## 🚀 Getting Started

**New to n8n?** Follow our [structured learning path](./docs/learning-path.md) for a week-by-week guide from beginner to expert!

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

### Study Materials in This Repository
- **[Getting Started Guide](./docs/getting-started.md)** - Your first workflow step-by-step
- **[Learning Path](./docs/learning-path.md)** - Structured curriculum with checkpoints
- **[Core Concepts](./docs/core-concepts.md)** - Deep dive into n8n fundamentals
- **[Best Practices](./docs/best-practices.md)** - Production-ready patterns
- **[Advanced Topics](./docs/advanced-topics.md)** - Scaling, optimization, and custom nodes
- **[Glossary](./docs/glossary.md)** - Complete terminology reference
- **[Workflow Examples](./examples/README.md)** - Importable workflow templates

### Official Documentation
- [n8n Documentation](https://docs.n8n.io/)
- [n8n Community](https://community.n8n.io/)
- [n8n GitHub](https://github.com/n8n-io/n8n)

### Learning Materials
- [n8n Academy](https://docs.n8n.io/courses/)
- [Workflow Templates](https://n8n.io/workflows)
- [YouTube Tutorials](https://www.youtube.com/c/n8n-io)

### Advanced Topics
- [Custom Nodes Development](./docs/advanced-topics.md#custom-node-development)
- [Self-hosting Configuration](./docs/advanced-topics.md#scaling-n8n)
- [Scaling n8n](./docs/advanced-topics.md#scaling-n8n)
- [API Integration Patterns](./docs/advanced-topics.md#integration-patterns)

## 🤝 Contributing

We welcome contributions! See [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines on:
- Adding workflow examples
- Improving documentation
- Sharing tips and tricks
- Reporting issues

Feel free to add your own workflow examples, notes, and learnings to this repository.

## 📝 License

This study repository is for educational purposes.

---

## 🚦 Quick Start Paths

### Path 1: I Want to Learn n8n
1. Read [Getting Started](./docs/getting-started.md)
2. Follow the [Learning Path](./docs/learning-path.md)
3. Import [example workflows](./examples/README.md)
4. Build your first automation!

### Path 2: I Have a Specific Task
1. Check [workflow examples](./examples/README.md) for similar patterns
2. Review [best practices](./docs/best-practices.md) for the task type
3. Use [core concepts](./docs/core-concepts.md) as reference
4. Build and test your workflow

### Path 3: I'm Already Using n8n
1. Explore [advanced topics](./docs/advanced-topics.md)
2. Review [best practices](./docs/best-practices.md) for optimization
3. Learn about [scaling](./docs/advanced-topics.md#scaling-n8n)
4. Consider [contributing](./CONTRIBUTING.md) your knowledge!

**Questions?** Check the [Glossary](./docs/glossary.md) or ask in the [n8n Community](https://community.n8n.io/)
