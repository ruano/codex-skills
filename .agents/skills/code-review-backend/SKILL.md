---
name: code-review-backend
description: General backend code quality review
---

## Instructions

- Apply SOLID principles
- Identify code smells
- Check error handling
- Evaluate readability and maintainability
- Suggest refactoring when needed
- Prefer Span/ReadOnlySpan over Substring in allocation-sensitive parsing paths

## Questions to ask:

### Edge cases:

- Are nulls handled correctly? 
- Are timeouts handled? 
- Is there a proper error boundary? 
- Is there a recovery path? 
- What happens under partial failure? 
- What happens with invalid or unexpected input? 

### Performance & Scalability:

- Any N+1 query risks? 
- Potential memory leaks? 
- Cache invalidation concerns? 
- Resource locking or contention? 
- Excessive allocations or unnecessary I/O? 
- Will this scale under load? 

### Production Readiness

- Are logs meaningful and actionable? 
- Is monitoring/observability in place? 
- Is there a rollback strategy? 
- Is backup/recovery considered? 
- Are retries/idempotency handled correctly? 
- Are failures visible and traceable?

## Philosophy

Prioritize:

- Correctness
- Reliability 
- Resilience 
- Observability 
- Performance 
- Maintainability 

Only then discuss formatting and style.

## Output Format

- Findings
- Suggested improvements
