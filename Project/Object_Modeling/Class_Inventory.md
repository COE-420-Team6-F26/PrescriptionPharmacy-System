# Class Inventory / Consolidation Record  

## 1. Approved Classes  

| Class ID | Class Name | Purpose/Responsibility | Related Use Case(s) | Contributor |
|---|---|---|---|---|
| C01 | Patient | Represents a registered patient who can log in, request prescription fills, view status changes, and view prescription information | UC-01, UC-02, UC-12, UC-15, UC-16 | Haya |
| C02 | Pharmacy Staff | Represents pharmacy employees responsible for managing prescriptions, reviewing refill requests and history, and updating inventory and status | UC-03, UC-05, UC-06, UC-07, UC-09, UC-10, UC-11, UC-12, UC-17, UC-19, UC-20 | Haya |
| C03 | Pharmacy | Stores pharmacy location for when prescriptions are needed to be picked up by patients | UC-18 | Haya |
| C04 | User (abstract) | Parent class for Patient and Pharmacy Staff, holding shared details: user ID, name, email, and login/logout. | UC-02 | Haya |
| C05 | Notification (abstract) | Base for all system messages: message text, sent time, send. | UC-12, UC-14 | Maryam |
| C06 | Status Notification | Tells the patient when a request is approved, rejected or ready. | UC-11, UC-12 | Maryam |
| C07 | LowStockAlert | Warns staff when stock falls below the threshold, and records acknowledgement | UC-13, UC-14 | Maryam |
| C08 | InventoryItem | Stores a medication's quantity and low-stock threshold. Checks whether stock is low. | UC-13, UC-14 | Maryam |
| C09 | Prescription | Stores a patient's prescription: medication, dosage, refills remaining, expiry date, and checks whether it is active | UC-06, UC-07, UC-10, UC-16 | Dima |
| C10 | Medication | Represents a medication: name, strength, form, that prescriptions and inventory items refer to | UC-06, UC-13 | Dima |
| C11 | RefillRequest | Represents a patient's refill request, its current stage, and checks eligibility | UC-01, UC-03, UC-08, UC-09, UC-11, UC-17, UC-19 | Dima |
| C12 | RefillStatusHistory | Records each status change of a refill request such as old/new status, time, staff member | UC-09, UC-20 | Dima |
| C13 | PickupOrder | Created when a refill is marked ready; links the request to the pharmacy pickup location | UC-04, UC-17, UC-18 | Dima |
| C14 | UserAccount | Stores user account information, including user ID, username, password hash, and account status. Handles authentication and account activation or deactivation. | UC-01, UC-02 | Yuchang |
| C15 | LoginSession | Represents an authenticated user session. Records session creation and expiration and validates whether a session is active. | UC-01, UC-02 | Yuchang |
| C16 | AccessControl | Checks whether a user has permission to access particular system functions based on their role. | UC-01, UC-02 | Yuchang |
| C17 | AuditLog | Records important system activities, including login attempts, account changes, and access events, to support monitoring and accountability. | UC-01, UC-02 | Yuchang |

## 2. Shared Classes  

Some classes appeared in more than one individual diagram. They are owned by one team member and were included in other members' diagrams only to show how their components connect.  

| Class | Owner | Also Shown In | Resolution |
|---|---|---|---|
| RefillRequest | Dima | Maryam | Kept as one class based on Dima's version; methods used by other components (updateStatus, getStatus) added |
| Patient | Haya | Maryam | Kept as one class based on Haya's version |
| PharmacyStaff | Haya | Maryam | Kept as one class based on Haya's version |
| RequestStatus | — | Maryam, Dima | Two different value lists unified into one |