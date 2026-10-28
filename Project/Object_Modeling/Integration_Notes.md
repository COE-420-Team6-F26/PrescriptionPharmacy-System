# *Integration Notes:*

## Changes Made During Integration

| # | Change | Reason | Affected Classes |
|---|---|---|---|
| 1 | Combined shared classes into single classes based on the owner's version | Classes appeared in other diagrams to show connections | RefillRequest, Patient, PharmacyStaff |
| 2 | Unified status type as RequestStatus = {PENDING, APPROVED, REJECTED, PREPARING, READY_FOR_PICKUP, COMPLETED} | Two different enum names and value lists | RefillRequest, RefillStatusHistory, StatusNotification |
| 3 | Removed password from User | Duplicated UserAccount.passwordHash | User, UserAccount |
| 4 | Replaced medicationName in InventoryItem with a "stocked as" association | Medication is its own class | InventoryItem, Medication |
| 5 | Added dateOfBirth to Patient | Required by register() and the Core Processes Matrix | Patient |
| 6 | Aligned method names and added missing parameters | Inconsistent names between classes | PharmacyStaff, Patient, RefillRequest |
| 7 | Added associations between components | Individual diagrams were not connected | Patient, PharmacyStaff, Prescription, PickupOrder, Pharmacy, Medication, InventoryItem |