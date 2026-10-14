# *Work Breakdown Structure:*

| ID | Task Name | Description | Predecessor(s) | Duration (Days) |
|---|---|---|---|---|
| T1 | Requirements Refinement | Review and finalize functional/non-functional requirements, use cases, actors, and system scope for the prescription refill and pharmacy pickup system. | — | 3 |
| T2 | Database Design | Design the database structure for patients, user accounts, prescriptions, medications, refill requests, inventory, and pickup information. | T1 | 4 |
| T3 | UI/UX Design | Design the main interfaces for patients and pharmacy staff, including login, prescriptions, refill requests, inventory, and notifications. | T1 | 4 |
| T4 | Authentication & User Accounts | Implement registration, login, authentication, account management, and access control for patients and pharmacy staff. | T2, T3 | 4 |
| T5 | Prescription Management | Implement prescription creation, editing, searching, viewing, expiration checking, and refill information. | T4 | 5 |
| T6 | Refill Request Management | Implement prescription refill requests, eligibility checking, request status updates, and pickup-order information. | T5 | 5 |
| T7 | Inventory Management | Implement medication stock management, stock updates, stock deduction, inventory viewing, and low-stock threshold checking. | T2, T4 | 4 |
| T8 | Notification System | Implement notifications for refill status changes, pickup location information, and low-stock alerts. | T6, T7 | 3 |
| T9 | Patient Interface Integration | Connect the patient-side interface with authentication, prescription viewing, refill requests, status tracking, and notifications. | T3, T4, T5, T6, T8 | 4 |
| T10 | Pharmacy Staff Interface Integration | Connect the pharmacy-side interface with prescription management, refill processing, inventory management, and notifications. | T5, T6, T7, T8 | 4 |
| T11 | System Integration | Integrate all major modules and verify that data flows correctly between accounts, prescriptions, refills, inventory, and notifications. | T9, T10 | 4 |
| T12 | Functional Testing | Test registration, login, prescriptions, refill eligibility, inventory, notifications, and pickup-status workflows. | T11 | 5 |
| T13 | Bug Fixing & Validation | Fix identified defects and perform regression testing to verify that corrections do not break existing functionality. | T12 | 4 |
| T14 | Deployment Preparation & Documentation | Prepare the final system, database, user documentation, technical documentation, and deployment materials. | T13 | 3 |