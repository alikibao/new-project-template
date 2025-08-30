# .ai/external-apis/[service-name]/our-usage.md
## Service: [API Name]

### Why We Need It
[1-2 sentences on business purpose]

### Endpoints We'll Use
1. `GET /endpoint1` - For [purpose]
2. `POST /endpoint2` - For [purpose]

### Our Wrapper Interface
\```typescript
interface OurServiceClient {
  getBasicData(id: string): Promise<BasicData>
  // Start with ONLY what we need now
}
\```

### Not Implementing Yet
- Pagination
- Bulk operations
- Webhooks
- Advanced filters
