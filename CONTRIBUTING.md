# Contributing to n8n Study Repository

Thank you for your interest in contributing to this n8n study repository! This guide will help you add your own learnings, examples, and improvements.

## 🤝 How to Contribute

### Types of Contributions

1. **Workflow Examples**
   - Share working n8n workflows
   - Document use cases
   - Add explanatory comments

2. **Documentation Improvements**
   - Fix typos or errors
   - Add clarifications
   - Expand existing topics
   - Add new topics

3. **Learning Resources**
   - Share useful tutorials
   - Add video links
   - Link to helpful articles

4. **Tips and Tricks**
   - Share best practices
   - Add optimization techniques
   - Document common pitfalls

## 📝 Contribution Guidelines

### Adding Workflow Examples

When contributing a workflow example:

1. **Export your workflow** as JSON from n8n
2. **Save it** in the `examples/` directory
3. **Use descriptive naming**: `feature-description.json`
4. **Add documentation** to `examples/README.md`

Example entry in `examples/README.md`:

```markdown
### Your Workflow Name
**File**: `your-workflow.json`
**Purpose**: Brief description of what it does
**Nodes**: List main nodes used

This workflow demonstrates:
- Key feature 1
- Key feature 2
- Key feature 3
```

#### Workflow Checklist

- [ ] Workflow works correctly
- [ ] Sensitive data removed (API keys, passwords)
- [ ] Nodes are clearly named
- [ ] Add notes/comments for complex parts
- [ ] Pin sample data for testing
- [ ] Document in examples/README.md

### Improving Documentation

When updating documentation:

1. **Keep it clear and concise**
2. **Use examples** to illustrate concepts
3. **Follow existing formatting** style
4. **Test code examples** before submitting
5. **Use proper markdown** formatting

#### Documentation Structure

```markdown
# Main Heading

Brief introduction

## Section Heading

Explanation with examples

### Subsection

Detailed content

```code
Example code
```

**Tips**:
- Tip content
```

### Adding Resources

When adding external resources:

1. **Verify links** are working
2. **Provide context** for the resource
3. **Categorize appropriately**
4. **Prefer official sources** when available

## 🎨 Style Guide

### Markdown Formatting

- Use `#` for headings (single space after #)
- Use `**bold**` for emphasis
- Use `code` for inline code
- Use triple backticks for code blocks
- Use `-` for unordered lists
- Use `1.` for ordered lists

### Code Examples

Always specify the language for syntax highlighting:

````markdown
```javascript
// JavaScript code
const example = "hello";
```

```json
{
  "key": "value"
}
```

```bash
# Bash commands
npm install n8n
```
````

### Naming Conventions

- **Files**: Use lowercase with hyphens: `my-example.json`
- **Folders**: Use lowercase: `examples`, `docs`
- **Headings**: Use title case: "Getting Started Guide"

## 🔧 Setting Up for Development

### Fork and Clone

```bash
# Fork the repository on GitHub, then:
git clone https://github.com/YOUR-USERNAME/n8n.git
cd n8n

# Add upstream remote
git remote add upstream https://github.com/najung-h/n8n.git
```

### Create a Branch

```bash
# Create a new branch for your contribution
git checkout -b add-my-feature
```

### Make Changes

1. Add your content
2. Test thoroughly
3. Review your changes

### Commit Your Changes

```bash
# Add files
git add .

# Commit with descriptive message
git commit -m "Add workflow example for data transformation"
```

### Submit a Pull Request

```bash
# Push to your fork
git push origin add-my-feature
```

Then create a Pull Request on GitHub.

## ✅ Pull Request Checklist

Before submitting a pull request:

- [ ] Changes are tested and working
- [ ] No sensitive information included
- [ ] Documentation is updated
- [ ] Code examples are tested
- [ ] Markdown is properly formatted
- [ ] Links are working
- [ ] Commit messages are descriptive

## 📋 Workflow Example Template

Use this template when adding new workflow examples:

```json
{
  "name": "Descriptive Workflow Name",
  "nodes": [
    {
      "parameters": {},
      "name": "Clear Node Name",
      "type": "n8n-nodes-base.nodeType",
      "notes": "Explanation of what this node does",
      "position": [250, 300]
    }
  ],
  "connections": {},
  "active": false,
  "settings": {},
  "tags": [
    {
      "name": "category",
      "id": "1"
    }
  ]
}
```

## 📖 Documentation Template

Use this template for new documentation files:

```markdown
# Topic Title

Brief introduction explaining what this document covers.

## Overview

High-level overview of the topic.

## Main Concepts

### Concept 1

Explanation with examples

### Concept 2

Explanation with examples

## Practical Examples

### Example 1

Step-by-step example

## Best Practices

1. Practice 1
2. Practice 2

## Common Pitfalls

- Pitfall and how to avoid it

## Resources

- [Resource Name](URL)
```

## 🐛 Reporting Issues

### Found a Bug?

If you find an error in the documentation or examples:

1. **Check** if it's already reported
2. **Create an issue** with:
   - Clear title
   - Description of the problem
   - Steps to reproduce (if applicable)
   - Expected vs actual behavior
   - Screenshots (if helpful)

### Suggesting Enhancements

Have an idea to improve the study materials?

1. **Open an issue** with:
   - Clear description of the enhancement
   - Why it would be valuable
   - Example of how it would work

## 🎓 Learning Resources to Share

When sharing learning resources, include:

- **Title** of the resource
- **Type**: Video, article, course, etc.
- **Level**: Beginner, intermediate, advanced
- **Brief description**
- **Why it's valuable**
- **Working link**

Example:

```markdown
### n8n Automation Basics
**Type**: Video Series
**Level**: Beginner
**Link**: [YouTube](https://example.com)

This series covers the fundamentals of n8n automation with
practical examples and clear explanations. Great for beginners
who prefer video learning.
```

## 🏆 Recognition

Contributors will be:
- Listed in the README (if desired)
- Credited in their contributions
- Appreciated by the community!

## 💬 Questions?

- Open an issue for questions
- Tag it with `question` label
- Community members will help

## 📜 Code of Conduct

- Be respectful and inclusive
- Help others learn
- Give constructive feedback
- Celebrate successes
- Learn together

## 🙏 Thank You!

Every contribution, no matter how small, helps others learn n8n more effectively. Thank you for being part of this learning community!

---

**Ready to contribute?** Pick an area above and start sharing your knowledge! 🚀
