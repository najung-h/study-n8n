# Advanced n8n Topics

Deep dive into advanced concepts and techniques for power users.

## Advanced Expressions

### Complex Data Access

```javascript
// Access nested objects
{{ $json.user.profile.settings.theme }}

// Access array elements
{{ $json.items[0].name }}

// Loop through array with map
{{ $json.items.map(item => item.price).join(', ') }}

// Filter arrays
{{ $json.users.filter(u => u.active === true) }}

// Reduce arrays
{{ $json.orders.reduce((sum, order) => sum + order.total, 0) }}
```

### Advanced String Manipulation

```javascript
// Regular expressions
{{ $json.email.match(/^[\w-\.]+@([\w-]+\.)+[\w-]{2,4}$/) }}

// String replacement
{{ $json.text.replace(/old/g, 'new') }}

// Template literals
{{ `User ${$json.name} has ${$json.points} points` }}

// String splitting and joining
{{ $json.tags.split(',').map(t => t.trim()).join(' | ') }}
```

### Date and Time Operations

```javascript
// Luxon date formatting
{{ $now.toFormat('yyyy-MM-dd HH:mm:ss') }}

// Date arithmetic
{{ $now.plus({ days: 7 }).toISO() }}
{{ $now.minus({ hours: 2 }).toFormat('HH:mm') }}

// Date comparison
{{ $now.diff($json.createdAt, 'days').days }}

// Parse custom date formats
{{ DateTime.fromFormat($json.date, 'dd/MM/yyyy') }}

// Time zones
{{ $now.setZone('America/New_York').toISO() }}
```

### Conditional Expressions

```javascript
// Ternary operator
{{ $json.status === 'active' ? 'Enabled' : 'Disabled' }}

// Nullish coalescing
{{ $json.name ?? 'Unknown' }}

// Optional chaining
{{ $json.user?.profile?.email }}

// Complex conditions
{{ $json.score > 80 && $json.verified ? 'Premium' : 'Standard' }}
```

## Performance Optimization

### 1. Batch Processing Strategies

```javascript
// Process in chunks of 100
Split In Batches (batchSize: 100)
  → Process Items
  → Aggregate Results
  → Continue Until Done
```

### 2. Caching Patterns

```javascript
// In Code node
const cache = {};

// Check cache first
if (cache[key]) {
  return cache[key];
}

// Fetch and cache
const data = await fetchData();
cache[key] = data;
return data;
```

### 3. Parallel Processing

- Use multiple branches for independent operations
- Process different data sources simultaneously
- Merge results at the end

### 4. Database Optimization

- Use indexes on frequently queried fields
- Limit result sets with WHERE clauses
- Use batch inserts instead of individual records
- Implement connection pooling

## Custom Node Development

### When to Create Custom Nodes

- Frequently used operation not available in n8n
- Complex logic that's hard to maintain in Function nodes
- Reusable across multiple workflows
- Better performance needed

### Basic Custom Node Structure

```typescript
import {
  IExecuteFunctions,
  INodeExecutionData,
  INodeType,
  INodeTypeDescription,
} from 'n8n-workflow';

export class MyCustomNode implements INodeType {
  description: INodeTypeDescription = {
    displayName: 'My Custom Node',
    name: 'myCustomNode',
    group: ['transform'],
    version: 1,
    description: 'Custom node description',
    defaults: {
      name: 'My Custom Node',
    },
    inputs: ['main'],
    outputs: ['main'],
    properties: [
      // Node parameters
    ],
  };

  async execute(this: IExecuteFunctions): Promise<INodeExecutionData[][]> {
    const items = this.getInputData();
    const returnData: INodeExecutionData[] = [];
    
    // Process items
    for (let i = 0; i < items.length; i++) {
      // Your logic here
    }
    
    return [returnData];
  }
}
```

## Scaling n8n

### Horizontal Scaling

```yaml
# docker-compose.yml for scaled setup
version: '3.8'
services:
  n8n-master:
    image: n8nio/n8n
    environment:
      - N8N_EXECUTIONS_MODE=queue
      - QUEUE_BULL_REDIS_HOST=redis
    
  n8n-worker:
    image: n8nio/n8n
    command: worker
    environment:
      - N8N_EXECUTIONS_MODE=queue
      - QUEUE_BULL_REDIS_HOST=redis
    deploy:
      replicas: 3
    
  redis:
    image: redis:alpine
```

### Database Optimization

- Use PostgreSQL for production
- Enable connection pooling
- Regular database maintenance
- Archive old executions

### Queue Configuration

```bash
# Environment variables
export EXECUTIONS_MODE=queue
export QUEUE_BULL_REDIS_HOST=localhost
export QUEUE_BULL_REDIS_PORT=6379
export QUEUE_HEALTH_CHECK_ACTIVE=true
```

## Security Best Practices

### 1. Secure Webhook Endpoints

```javascript
// Verify webhook signatures
const crypto = require('crypto');

function verifySignature(payload, signature, secret) {
  const hash = crypto
    .createHmac('sha256', secret)
    .update(payload)
    .digest('hex');
  
  return crypto.timingSafeEqual(
    Buffer.from(signature),
    Buffer.from(hash)
  );
}
```

### 2. Input Validation

```javascript
// Validate and sanitize inputs
function validateEmail(email) {
  const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  return re.test(email);
}

function sanitizeInput(input) {
  return input
    .trim()
    .replace(/[<>]/g, '');
}
```

### 3. Rate Limiting

```javascript
// Implement rate limiting
const rateLimit = new Map();

function checkRateLimit(ip, limit = 100, window = 60000) {
  const now = Date.now();
  const requests = rateLimit.get(ip) || [];
  
  // Remove old requests
  const recent = requests.filter(time => now - time < window);
  
  if (recent.length >= limit) {
    return false;
  }
  
  recent.push(now);
  rateLimit.set(ip, recent);
  return true;
}
```

### 4. Secrets Management

- Use environment variables for secrets
- Rotate credentials regularly
- Use least privilege access
- Enable audit logging

## Advanced Workflow Patterns

### 1. Event-Driven Architecture

```
Event Source → Webhook → Validate → Route by Type
                                     ├→ Process Type A → Store
                                     ├→ Process Type B → Store
                                     └→ Process Type C → Store
```

### 2. Saga Pattern (Distributed Transactions)

```
Start Transaction
  → Step 1 (compensate: Undo Step 1)
  → Step 2 (compensate: Undo Step 2)
  → Step 3 (compensate: Undo Step 3)
  → Commit or Rollback
```

### 3. Circuit Breaker

```javascript
// Circuit breaker implementation
class CircuitBreaker {
  constructor(threshold = 5, timeout = 60000) {
    this.failureCount = 0;
    this.threshold = threshold;
    this.timeout = timeout;
    this.state = 'CLOSED';
    this.nextAttempt = Date.now();
  }
  
  async execute(fn) {
    if (this.state === 'OPEN') {
      if (Date.now() < this.nextAttempt) {
        throw new Error('Circuit breaker is OPEN');
      }
      this.state = 'HALF_OPEN';
    }
    
    try {
      const result = await fn();
      this.onSuccess();
      return result;
    } catch (error) {
      this.onFailure();
      throw error;
    }
  }
  
  onSuccess() {
    this.failureCount = 0;
    this.state = 'CLOSED';
  }
  
  onFailure() {
    this.failureCount++;
    if (this.failureCount >= this.threshold) {
      this.state = 'OPEN';
      this.nextAttempt = Date.now() + this.timeout;
    }
  }
}
```

### 4. Retry with Exponential Backoff

```javascript
async function retryWithBackoff(fn, maxRetries = 3, baseDelay = 1000) {
  for (let i = 0; i < maxRetries; i++) {
    try {
      return await fn();
    } catch (error) {
      if (i === maxRetries - 1) throw error;
      
      const delay = baseDelay * Math.pow(2, i);
      await new Promise(resolve => setTimeout(resolve, delay));
    }
  }
}
```

## Integration Patterns

### 1. Polling vs Webhooks

**Polling** (Pull):
- Check for new data periodically
- Simpler to implement
- Higher latency
- More resource intensive

**Webhooks** (Push):
- Receive data in real-time
- More complex setup
- Lower latency
- More efficient

### 2. API Pagination Handling

```javascript
// Handle paginated API responses
const allResults = [];
let page = 1;
let hasMore = true;

while (hasMore) {
  const response = await fetch(`${url}?page=${page}`);
  const data = await response.json();
  
  allResults.push(...data.results);
  hasMore = data.hasNext;
  page++;
  
  // Rate limiting
  await new Promise(resolve => setTimeout(resolve, 1000));
}

return allResults;
```

### 3. GraphQL Integration

```javascript
// GraphQL query in HTTP Request node
{
  "query": `
    query GetUser($id: ID!) {
      user(id: $id) {
        name
        email
        posts {
          title
          content
        }
      }
    }
  `,
  "variables": {
    "id": "{{ $json.userId }}"
  }
}
```

## Monitoring and Observability

### 1. Workflow Metrics

```javascript
// Track execution metrics
const startTime = Date.now();

// Your workflow logic

const duration = Date.now() - startTime;
const metrics = {
  workflow: $workflow.name,
  duration,
  itemsProcessed: $items.length,
  timestamp: $now.toISO()
};

// Send to monitoring system
```

### 2. Health Checks

```javascript
// Implement health check endpoint
GET /healthz
→ Check Database Connection
→ Check Redis Connection
→ Check Critical Services
→ Return Status
```

### 3. Alerting

- Set up error notifications
- Monitor execution times
- Track failure rates
- Alert on threshold breaches

## Testing Strategies

### 1. Unit Testing Workflows

- Test individual nodes with pinned data
- Verify expressions produce expected outputs
- Test error handling paths

### 2. Integration Testing

- Test end-to-end workflows
- Use test credentials
- Verify external integrations
- Test with production-like data

### 3. Load Testing

- Test with large datasets
- Measure execution times
- Identify bottlenecks
- Optimize performance

## Deployment Strategies

### 1. Blue-Green Deployment

- Maintain two identical environments
- Deploy to inactive environment
- Test thoroughly
- Switch traffic
- Keep old version for rollback

### 2. Canary Deployment

- Deploy to small subset of users
- Monitor metrics
- Gradually increase traffic
- Rollback if issues detected

### 3. CI/CD Pipeline

```yaml
# .github/workflows/deploy.yml
name: Deploy n8n Workflows
on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Export workflows
        run: |
          # Export from dev
          # Import to production
```

## Resources

- [n8n GitHub](https://github.com/n8n-io/n8n)
- [Custom Nodes Documentation](https://docs.n8n.io/integrations/creating-nodes/)
- [n8n API Documentation](https://docs.n8n.io/api/)
- [Community Templates](https://n8n.io/workflows)
