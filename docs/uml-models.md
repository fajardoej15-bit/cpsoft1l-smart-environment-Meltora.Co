# Activity 03 Deliverable A: UML Model Pack (Meltora.Co)

## 1. Class Diagram (Domain Model)
The domain model consists of the following primary entities:
* *User:* Handles customer and staff authentication profiles (userId, name, email, role).
* *MenuItem:* Represents bakery items (itemId, name, category, price, isAvailable).
* *Order:* Core transaction entity (orderId, customerId, items, totalAmount, status, createdAt).
* *OrderController:* Manages order creation, retrieval, and status updates.
* *PaymentService:* Handles checkout payment processing.
* *NotificationService:* Dispatches real-time WebSocket events to kitchen and customer clients.

## 2. Sequence Diagram (UC-01: Place Order & Kitchen Notification)
1. Customer submits cart checkout via POST /api/orders.
2. OrderController validates item availability with InventoryService.
3. PaymentService processes transaction authorization.
4. Order record is saved to MongoDB Atlas with status RECEIVED.
5. NotificationService triggers Socket.io broadcast event NEW_ORDER_DISPATCH to Kitchen Dashboard.
6. Customer UI receives order confirmation modal and real-time status tracker link (<1.5s total execution).

## 3. Package & Component Overview
* *Presentation Package:* Web Client UI & Kitchen Dashboard UI.
* *Application Services Package:* OrderController, CatalogController, PaymentController.
* *Domain Engine Package:* OrderEngine, InventoryEngine, NotificationService.
* *Data Layer Package:* Mongoose Repositories connecting to MongoDB Atlas.