# AI Development Instructions (Persistent)

## Project Context
- Stage: [prototype|mvp|production]
- Development Approach: [pragmatic-tdd|classic-tdd|test-after]
- Primary Goal: [One sentence description]
- Current Sprint: [Link to mvp.md]

## Code Standards
### DO:
- Write simple, readable code
- Use existing patterns in codebase
- Add types/interfaces (TypeScript) or type hints (Python)
- Handle basic errors (try/catch)
- Comment WHY, not WHAT

### DON'T:
- Add caching (unless explicit in task)
- Create abstractions for single-use code
- Add middleware/interceptors in v1
- Implement complex auth flows
- Over-engineer error handling
- Add logging frameworks (use console.log)

## File Structure Rules
- Controllers/Routes: Max 150 lines
- Services/Logic: Max 200 lines
- Single responsibility per file
- Flat structure until 10+ files in directory

## Development Protocol

### For Pragmatic TDD (Recommended):
1. Write interface/contract first
2. Write 1-2 core test cases (happy path + main error)
3. Implement minimal code to pass
4. Add edge case tests only after working
5. Refactor only if tests still pass

### For Classic TDD:
1. Write complete test suite first
2. Run tests (confirm they fail)
3. Implement minimal passing code
4. Refactor with green tests
5. Add tests for any discovered edge cases

### For Test-After (Prototype Phase):
1. Clarify requirements
2. Propose minimal solution
3. Implement after approval
4. Add tests for critical paths only
5. Document untested edge cases

## Test Writing Rules (When Using TDD)
- Test behavior, not implementation
- One assertion per test preferred
- Test names describe expected behavior
- No mocking unless absolutely necessary
- Prefer integration tests over unit tests for APIs
- Max 3x LOC ratio (tests:implementation)

## Current Patterns
[Update this section as patterns emerge]
- API responses: `{ success: boolean, data?: any, error?: string }`
- Error handling: Simple try/catch with 500 response
- Database: Direct queries, no ORM yet
- Test structure: Given/When/Then format
