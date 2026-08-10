# Activity 03 Deliverable C: Pattern Decision Package (Meltora.Co)

## 1. ACCEPTED PATTERN: Observer Pattern (Socket.io WebSockets)
* *Context:* Customer and kitchen status displays require continuous synchronization without manual browser reloads.
* *Problem Solved:* Prevents heavy HTTP REST polling loops every few seconds to check if an order is BAKING, READY_FOR_PICKUP, or DELIVERED.
* *Implementation:* Kitchen staff update order state $\rightarrow$ NotificationService emits WebSocket event $\rightarrow$ Customer UI updates real-time status badge instantly.
* *Trade-off Accepted:* Server maintains active WebSocket connection states in exchange for reducing network overhead by 85% and enabling sub-2 second order updates.

## 2. REJECTED PATTERN: Microservices Architecture & CQRS
* *Context Evaluated:* Splitting catalog, ordering, and payment operations into standalone microservices with separate read/write databases.
* *Reason for Rejection:* Over-engineering for Meltora.Co's current operational scale. Microservices introduce network hop latency, distributed deployment complexity, and unnecessary cloud hosting costs.
* *Decision Rule:* Retain Modular Monolith until transaction throughput exceeds 10,000 orders/hour.