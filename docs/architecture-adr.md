# Activity 03 Deliverable D: Architectural Decision Record (Meltora.Co)

## Architectural Decision Record (ADR-01)
* *Title:* Modular Monolith Architecture for Meltora.Co Bakery Platform
* *Status:* Accepted
* *Context:* The bakery platform requires reliable order ingestion, inventory verification, secure checkout, and real-time kitchen tracking.
* *Decision:* Adopt a *Modular Monolith* architectural style using Node.js, Express.js, and MongoDB Atlas.
* *Consequences:*
  * *Positive:* Fast deployment cycle, zero inter-service network overhead, shared memory state for fast order validation, and fits completely within free-tier cloud hosting.
  * *Negative:* System components scale together as a single process rather than independently.