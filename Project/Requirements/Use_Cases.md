# Use Case Descriptions

## *Student 1 Contributions (Haya)*  

| UC ID | Use Case Name | Primary Actor | Short Description |
|-------|---------------|---------------|-------------------|
| UC-01 | Input Refill Request | Patient | The patient fills in a refill request for an active prescription |
| UC-02 | Login | Patient | The patient logs in to their account using their credentials |
| UC-03 | View Queue of Incoming Requests | Pharmacy Staff | The pharmacy staff views a list of incoming refill requests given by the system |
| UC-04 | Inform Pickup | System | The system notifies the patient of the ready prescription that has been refilled |
| UC-05 | Check User Details | Pharmacy Staff | The pharmacy staff checks on the patient's details (medications etc.); this will help determine whether to accept or reject the patient's prescription refill request |

## *Student 2 Contributions (Dima)*  

| UC ID | Use Case Name | Primary Actor | Short Description |
|-------|---------------|---------------|-------------------|
| UC-06 | Create New Prescription | Pharmacy Staff | A staff member enters a new prescription record for a patient, including medication, dosage, and allowed refills |
| UC-07 | Edit Existing Prescription | Pharmacy Staff | A staff member modifies the dosage or refill count on an existing prescription when a treatment changes |
| UC-08 | Validate Refill Eligibility | System | The system checks whether a prescription is expired or has remaining refills before allowing the request to proceed |
| UC-09 | Update Next Stage | Pharmacy Staff | Staff member advances a refill request to the next stage/fulfillment stage in the correct sequence |
| UC-10 | Search Patient Records | Pharmacy Staff | Staff searches for a specific patient's prescription records |

## *Student 3 Contributions (Maryam)*  

| UC ID | Use Case Name | Primary Actor | Short Description |
|-------|---------------|---------------|-------------------|
| UC-11 | Reject Refill Request | Pharmacy Staff | Staff reviews a refill request and rejects it with a specified reason, which is recorded and shown to the patient |
| UC-12 | Receive Order Status Notification | Patient | The system notifies the patient whenever their refill order's status changes |
| UC-13 | Update Inventory Stock | Pharmacy Staff | Staff manually updates the quantity of a medication in the system after receiving new stock |
| UC-14 | Trigger Low Stock Alert | System (automated) | The system checks inventory levels and generates an alert when a medication falls below its threshold |
| UC-15 | Register New Patient Account | Patient | A new patient creates an account by providing personal and contact details to begin using the system |

## *Student 4 Contributions (Yuchang)*  

| UC ID | Use Case Name | Primary Actor | Short Description |
|-------|---------------|---------------|-------------------|
| UC-16 | View Active Prescriptions | Patient | The patient views their active prescriptions, including medication, dosage, and remaining refills |
| UC-17 | Mark Refill as Ready for Pickup | Pharmacy Staff | Pharmacy staff mark an approved refill request as ready after preparing the medication |
| UC-18 | View Pickup Location | Patient | The patient views the pharmacy location where their refill is available for pickup |
| UC-19 | View Refill Request Details | Pharmacy Staff | Pharmacy staff view the details of a selected refill request before processing it |
| UC-20 | View Refill Status History | Pharmacy Staff | Pharmacy staff views the previous statuses and timestamps associated with a refill request |  

---

# Use Case Relationships

| R-ID | Base UC | Related UC | Relationship | Justification |
|------|---------|------------|--------------|---------------|
| R-01 | UC-01 Input Refill Request | UC-02 Login | extend | Before a patient can fill in a refill request, they must be logged in and authenticated; since login is a mandatory prerequisite. This only occurs if the user is not logged in |
| R-02 | UC-03 View Queue of Incoming Requests | UC-05 Check User Details | extend | Viewing the queue works fine on its own, but checking a patient's details only happens when or if staff choose to inspect a specific request in order to accept/deny the refill request |
| R-03 | UC-05 Check User Details | UC-04 Inform Pickup | extend | Informing the patient of pickup happens only after the staff have checked user details and approved the request |
| R-04 | UC-11 Reject Refill Request | UC-12 Receive Order Status Notification | include | Rejecting a request always triggers a notification to the patient, so this step is a mandatory part of the base use case |
| R-05 | UC-13 Update Inventory Stock | UC-14 Trigger Low Stock Alert | extend | The low stock alert only fires if the updated quantity happens to fall below the threshold, a conditional outcome, not guaranteed every time |
| R-06 | UC-15 Register New Patient Account | UC-12 Receive Order Status Notification | include | Every successful registration always sends the patient a confirmation notification, reusing the same notification behavior rather than duplicating it |
| R-07 | UC-01 Input Refill Request | UC-08 Validate Refill Eligibility | include | Submitting a refill always requires checking that the prescription is unexpired and has refills left, so the check is a mandatory included step |
| R-08 | UC-09 Update Next Stage | UC-12 Receive Order Status Notification | include | Every stage change updates the request status and always triggers a patient notification, so the notification is a mandatory included step |
| R-09 | UC-17 Mark Refill as Ready for Pickup | UC-19 View Refill Request Details | include | Staff must open the request and check it is approved before marking it ready, so viewing details is a mandatory step |
| R-10 | UC-19 View Refill Request Details | UC-20 View Refill Status History | extend | Details work on their own. Staff open the history only when they need past statuses and timestamps |
| R-11 | UC-01 Input Refill Request | UC-16 View Active Prescriptions | include | A patient must view their active prescriptions to choose one to refill |
| R-12 | UC-17 Mark Refill as Ready for Pickup | UC-12 Receive Order Status Notification | include | Marking a refill ready always changes its status and notifies the patient |