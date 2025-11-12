# Learning Path for n8n

A structured guide to help you progress from beginner to advanced n8n user.

## 📚 Recommended Learning Path

### Week 1: Foundations (Beginner)

**Goal**: Understand n8n basics and create your first workflows

1. **Read**: [Getting Started Guide](./getting-started.md)
   - Install n8n using Docker or n8n.cloud
   - Complete your first workflow
   - Understand the n8n interface

2. **Study**: [Core Concepts](./core-concepts.md)
   - Understand nodes, triggers, and connections
   - Learn about data flow ($json, $items)
   - Practice basic expressions

3. **Practice**: Import and study example workflows
   - [Hello World](../examples/hello-world.json)
   - [HTTP Request](../examples/http-request.json)
   - Modify examples to understand how they work

4. **Exercise**: Build Your First Workflow
   - Create a workflow that fetches weather data
   - Display the current temperature
   - Format the output

**Resources**:
- [n8n Quickstart](https://docs.n8n.io/getting-started/quickstart/)
- [n8n YouTube - Basics](https://www.youtube.com/c/n8n-io)

---

### Week 2: Core Skills (Beginner to Intermediate)

**Goal**: Master essential n8n features

1. **Learn**: Expressions and Data Manipulation
   - Practice accessing nested data
   - Use built-in functions
   - Work with dates and strings

2. **Study**: [Best Practices](./best-practices.md)
   - Workflow naming conventions
   - Error handling basics
   - Data validation

3. **Practice**: Build Practical Workflows
   - Webhook receiver
   - Scheduled data sync
   - Email notifications

4. **Exercise**: Error Handling
   - Create a workflow that might fail
   - Add error handling
   - Implement retry logic

**Resources**:
- [n8n Expressions Reference](https://docs.n8n.io/code-examples/expressions/)
- [Common Workflow Patterns](https://n8n.io/workflows)

---

### Week 3: Integration & Automation (Intermediate)

**Goal**: Connect n8n to real services

1. **Configure**: Set up credentials
   - Gmail/Email
   - Slack or Discord
   - Database (optional)
   - Any API you use

2. **Build**: Real-World Automations
   - Email to Slack notifications
   - Form submission processor
   - Data backup automation
   - Report generator

3. **Study**: Integration Patterns
   - API authentication methods
   - Webhook security
   - Rate limiting
   - Pagination

4. **Exercise**: Multi-Step Workflow
   - Combine 3+ services
   - Add conditional logic
   - Implement error notifications

**Resources**:
- [n8n Integrations](https://n8n.io/integrations)
- [API Integration Best Practices](./best-practices.md#api-calls)

---

### Week 4: Advanced Techniques (Advanced)

**Goal**: Master advanced patterns and optimization

1. **Study**: [Advanced Topics](./advanced-topics.md)
   - Complex expressions
   - Performance optimization
   - Advanced workflow patterns

2. **Learn**: Sub-workflows and Modularity
   - Create reusable workflows
   - Design modular systems
   - Workflow organization

3. **Practice**: Advanced Patterns
   - Circuit breaker pattern
   - Retry with exponential backoff
   - Batch processing
   - Event-driven workflows

4. **Exercise**: Build a Complex System
   - Multi-workflow application
   - Error recovery system
   - Data processing pipeline

**Resources**:
- [Custom Nodes Development](https://docs.n8n.io/integrations/creating-nodes/)
- [n8n Advanced Courses](https://docs.n8n.io/courses/)

---

### Ongoing: Mastery & Contribution

**Goal**: Become an n8n expert

1. **Optimize**: Review and Improve
   - Audit existing workflows
   - Optimize performance
   - Implement monitoring

2. **Scale**: Production Deployment
   - Self-host n8n
   - Configure for scale
   - Implement security best practices

3. **Contribute**: Give Back
   - Share workflows with community
   - Create custom nodes
   - Help others in forums

4. **Stay Updated**: Continuous Learning
   - Follow n8n releases
   - Join community events
   - Explore new integrations

**Resources**:
- [n8n Community Forum](https://community.n8n.io/)
- [n8n GitHub](https://github.com/n8n-io/n8n)
- [n8n Blog](https://blog.n8n.io/)

---

## 🎯 Skill Checkpoints

### Beginner ✅
- [ ] Installed and accessed n8n
- [ ] Created first workflow
- [ ] Understand basic nodes (Manual Trigger, Set, HTTP Request)
- [ ] Can use simple expressions
- [ ] Executed a workflow successfully

### Intermediate ✅
- [ ] Created 5+ workflows
- [ ] Set up credentials for external services
- [ ] Implemented error handling
- [ ] Used webhooks
- [ ] Created scheduled workflows
- [ ] Worked with conditional logic (IF nodes)

### Advanced ✅
- [ ] Built complex multi-step workflows
- [ ] Created sub-workflows
- [ ] Optimized workflow performance
- [ ] Implemented advanced error handling
- [ ] Used Code/Function nodes effectively
- [ ] Worked with databases
- [ ] Created reusable workflow patterns

### Expert ✅
- [ ] Self-hosted n8n in production
- [ ] Created custom nodes
- [ ] Scaled n8n for high load
- [ ] Contributed to n8n community
- [ ] Mentored others
- [ ] Published workflow templates

---

## 📖 Quick Reference by Topic

### Getting Started
- [Installation & Setup](./getting-started.md#installation)
- [First Workflow](./getting-started.md#your-first-workflow)
- [Understanding the Interface](./getting-started.md)

### Core Concepts
- [Nodes & Triggers](./core-concepts.md#nodes)
- [Data Flow](./core-concepts.md#data-flow)
- [Expressions](./core-concepts.md#expressions)
- [Credentials](./core-concepts.md#credentials)

### Practical Guides
- [Error Handling](./core-concepts.md#error-handling)
- [Webhooks](./core-concepts.md#webhooks)
- [Sub-workflows](./core-concepts.md#sub-workflows)

### Best Practices
- [Workflow Design](./best-practices.md#workflow-design)
- [Security](./best-practices.md#security)
- [Performance](./best-practices.md#performance)
- [Testing](./best-practices.md#testing)

### Advanced
- [Custom Nodes](./advanced-topics.md#custom-node-development)
- [Scaling](./advanced-topics.md#scaling-n8n)
- [Advanced Patterns](./advanced-topics.md#advanced-workflow-patterns)
- [Optimization](./advanced-topics.md#performance-optimization)

### Reference
- [Glossary](./glossary.md)
- [Expression Variables](./glossary.md#expression-variables)
- [Common Abbreviations](./glossary.md#common-abbreviations)

---

## 🎓 Learning Tips

### 1. Learn by Doing
- Don't just read - build workflows
- Start simple, add complexity gradually
- Break when you get stuck, come back fresh

### 2. Use the Community
- Join the [n8n Community Forum](https://community.n8n.io/)
- Search for solutions before asking
- Share your learnings

### 3. Keep a Workflow Journal
- Document what you build
- Note challenges and solutions
- Track your progress

### 4. Build Real Projects
- Automate something you actually need
- Solve real problems
- Share useful workflows

### 5. Stay Curious
- Explore new nodes
- Try different approaches
- Learn from others' workflows

---

## 🚀 Project Ideas by Level

### Beginner Projects
1. **Daily Weather Email** - Send weather forecast every morning
2. **GitHub Star Tracker** - Track repository stars
3. **RSS to Slack** - Post new articles to Slack
4. **Form to Email** - Process form submissions
5. **URL Shortener** - Create short links via webhook

### Intermediate Projects
1. **Social Media Scheduler** - Post to multiple platforms
2. **Invoice Generator** - Create PDFs from data
3. **Task Sync** - Sync between todo apps
4. **Backup Automation** - Automated backups to cloud
5. **Price Monitor** - Track product prices, alert on changes

### Advanced Projects
1. **CRM Sync System** - Multi-directional data sync
2. **Custom API Gateway** - Build API with n8n
3. **Data Pipeline** - ETL for analytics
4. **Monitoring Dashboard** - Aggregate metrics
5. **Chatbot Backend** - Handle chatbot logic

---

## ✅ Next Steps

1. Choose your starting point based on experience
2. Follow the weekly plan
3. Complete exercises and checkpoints
4. Build real projects
5. Join the community
6. Share your progress!

Remember: Everyone learns at their own pace. Take your time, practice consistently, and don't hesitate to ask for help. Happy automating! 🎉
