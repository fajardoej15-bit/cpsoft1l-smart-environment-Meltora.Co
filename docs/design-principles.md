# Activity 03 Deliverable B: Design Principles Review (Meltora.Co)

## 1. Single Responsibility Principle (SRP)
* *Refactoring Strategy:* The monolithic OrderController was decomposed into specialized services:
  * CatalogService: Manages menu items and stock availability.
  * OrderProcessor: Validates cart calculations and state transitions.
  * NotificationService: Handles WebSocket event broadcasts to kitchen and customer clients.

## 2. Dependency Inversion Principle (DIP)
* High-level business logic in OrderProcessor depends on abstract repository interfaces (IOrderRepository, IPaymentGateway) rather than concrete ORM implementations (Mongoose).
* Allows mocking storage layers during automated testing and changing payment vendors without modifying order workflows.

## 3. Information Hiding & Encapsulation
* Domain entities use Data Transfer Objects (DTOs) like OrderResponseDTO to expose only customer-relevant fields to frontend clients while shielding internal MongoDB IDs and security tokens.