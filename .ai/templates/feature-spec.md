# .ai/templates/feature-spec.md
## Feature: [NAME]

### Single Objective
[One sentence description]

### Input/Output Contract (Define First!)
**Input**: [Specific data/params with types]
**Output**: [Expected response with types]

### Test Cases (For TDD Approach)
```typescript
// Happy Path
test('should [expected behavior]', () => {
  // Given
  const input = { /* specific data */ }
  // When
  const result = functionName(input)
  // Then
  expect(result).toEqual({ /* expected output */ })
})

// Main Error Case
test('should [error behavior] when [condition]', () => {
  // Given
  const invalidInput = { /* invalid data */ }
  // When/Then
  expect(() => functionName(invalidInput)).toThrow('[error message]')
})

// Edge Case (add after implementation works)
test('should handle [edge case]', () => {
  // Define edge case test
})
