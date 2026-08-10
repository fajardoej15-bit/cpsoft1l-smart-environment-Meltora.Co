# Activity 03 Deliverable E: Requirements Traceability Matrix (Meltora.Co)

| Req ID | Requirement Description | Design Element / Code Mapping | Verification Method |
| :--- | :--- | :--- | :--- |
| *FR-01* | Browse Menu & Categories | CatalogController & MenuCatalog UI Component | Jest Component Unit Test |
| *FR-02* | Customer Order Checkout | OrderProcessor.createOrder() & PaymentService | E2E Checkout Flow Test |
| *FR-03* | Real-Time Kitchen Dispatch | NotificationService & Observer Pattern Broadcast | WebSocket Integration Test |
| **NFR-01**| Sub-2 Second Status Sync | Socket.io Real-Time Push Architecture | Latency Profiling (<1.2s avg) |
| **NFR-03**| Secure Customer Auth | JWT Authentication Middleware & DTO Filtering | API Endpoint Security Audit |