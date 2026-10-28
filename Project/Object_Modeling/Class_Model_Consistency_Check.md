# *Class Model Consistency Check:*

## 1. Consistency with Use Cases

| Use Case | Supporting Classes |
|---|---|
| UC-01 Input Refill Request | Patient, Prescription, RefillRequest |
| UC-02 Login | User, UserAccount, LoginSession, AccessControl, AuditLog |
| UC-03 View Queue of Incoming Requests | PharmacyStaff, RefillRequest |
| UC-04 Inform Pickup | PickupOrder, Pharmacy, StatusNotification |
| UC-05 Check User Details | PharmacyStaff, Patient |
| UC-06 Create New Prescription | PharmacyStaff, Prescription, Medication |
| UC-07 Edit Existing Prescription | PharmacyStaff, Prescription |
| UC-08 Validate Refill Eligibility | RefillRequest, Prescription |
| UC-09 Update Next Stage | RefillRequest, RefillStatusHistory |
| UC-10 Search Patient Records | PharmacyStaff, Patient, Prescription |
| UC-11 Reject Refill Request | RefillRequest, StatusNotification |
| UC-12 Receive Order Status Notification | Notification, StatusNotification, Patient |
| UC-13 Update Inventory Stock | PharmacyStaff, InventoryItem |
| UC-14 Trigger Low Stock Alert | InventoryItem, LowStockAlert |
| UC-15 Register New Patient Account | Patient, UserAccount |
| UC-16 View Active Prescriptions | Patient, Prescription |
| UC-17 Mark Refill as Ready for Pickup | RefillRequest, PickupOrder |
| UC-18 View Pickup Location | PickupOrder, Pharmacy |
| UC-19 View Refill Request Details | PharmacyStaff, RefillRequest |
| UC-20 View Refill Status History | RefillStatusHistory |

## 2. Consistency with DFD

| DFD Element | Related Classes |
|---|---|
| P1 Manage User Accounts | User, UserAccount, LoginSession, AccessControl, AuditLog |
| P2 Manage Refill Requests | RefillRequest, RefillStatusHistory, PickupOrder |
| P3 Manage Prescriptions | Prescription, Medication |
| P4 Notification Alerts | Notification, StatusNotification, LowStockAlert |
| P5 Manage Inventory | InventoryItem |
| Data Store: Patient & Prescription Data | User, Patient, UserAccount, Prescription, Medication |
| Data Store: Refill & Inventory Data | RefillRequest, RefillStatusHistory, PickupOrder, InventoryItem |
| External Entity: Patient | Patient |
| External Entity: Pharmacy Staff | PharmacyStaff |

## 3. Verification of Relationships and Multiplicities

| Relationship | Multiplicity | Justification |
|---|---|---|
| Patient — submits — RefillRequest | 1 — 0..* | A patient can submit many requests; each request belongs to one patient |
| Patient — holds — Prescription | 1 — 0..* | A patient can have many prescriptions; each belongs to one patient |
| Patient — receives — StatusNotification | 1 — 0..* | Notifications go only to the patient who owns the request |
| PharmacyStaff — manages — Prescription | 1..* — 0..* | Staff create and edit prescriptions |
| PharmacyStaff — reviews — RefillRequest | 0..1 — 0..* | A request is reviewed by one staff member, or none yet |
| PharmacyStaff — works at — Pharmacy | 0..* — 1 | Each staff member works at one pharmacy |
| PharmacyStaff — update — InventoryItem | 0..* — 0..* | Only pharmacy staff can update stock |
| PharmacyStaff — is alerted by — LowStockAlert | 1..* — 0..* | Low stock alerts are sent to pharmacy staff |
| Prescription — refilled by — RefillRequest | 1 — 0..* | A prescription can be refilled many times |
| Prescription — prescribes — Medication | 0..* — 1 | Each prescription is for one medication |
| Medication — stocked as — InventoryItem | 1 — 1 | Each medication has one inventory record |
| RefillRequest — records — RefillStatusHistory (composition) | 1 — 1..* | Every status change is saved; history cannot exist without its request |
| RefillRequest — produces — PickupOrder | 1 — 0..1 | A pickup order is created only when the refill is ready |
| RefillRequest — triggers — StatusNotification | 1 — 0..* | A notification is sent on every status change |
| PickupOrder — collected at — Pharmacy | 0..* — 1 | Each order is collected at one pharmacy |
| UserAccount — account for — User | 1 — 0..1 | Each user has one account |
| UserAccount — creates — LoginSession | 1 — 0..* | One account can have many sessions |
| LoginSession — generates — AuditLog | 1 — 0..* | Session events are recorded in the audit log |
| AccessControl → UserAccount (dependency) | — | AccessControl uses UserAccount to check permissions |

### Inheritance

| Parent | Children | Justification |
|---|---|---|
| User | Patient, PharmacyStaff | Both are system users sharing ID, name, email, login/logout |
| Notification (abstract) | StatusNotification, LowStockAlert | Both are system messages sharing message, sent time, send() |