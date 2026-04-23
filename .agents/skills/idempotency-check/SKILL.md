---
name: idempotency-check
description: Ensure operations are safe for retries
---

## Instructions
- Verify existence of unique identifier (eventId, requestId)
- Check for deduplication logic
- Validate database constraints (unique keys)
- Ensure side effects are not duplicated
- Identify race conditions

## Output Format
- Idempotency risks
- Fix suggestions