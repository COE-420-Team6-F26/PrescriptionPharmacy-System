# *Class Distribution:*

| ID | Component Name | Responsibilities | Included Classes |
|---|---|---|---|
| CO1 | User & Access Management | Authentication, sessions, role-based access control, audit logging | User (abstract), Patient, PharmacyStaff, UserAccount, LoginSession, AccessControl, AuditLog |
| CO2 | Prescription Management | Prescription and medication records and validation | Prescription, Medication |
| CO3 | Refill & Pickup Processing | Refill requests, status tracking, history, pickup orders | RefillRequest, RefillStatusHistory, PickupOrder, Pharmacy, RequestStatus (enumeration) |
| CO4 | Inventory Management | Stock tracking and low-stock detection | InventoryItem |
| CO5 | Notification | Patient notifications and staff alerts | Notification (abstract), StatusNotification, LowStockAlert |