# Functional Requirements  

## *Student 1 Contributions (Haya)*  
**NFR-01**: (Scalability) The system shall support a 3x amount of registered patients and daily refill requests.    
**NFR-02**: (Maintainability) The system shall maintain regular updates and bug fixes to ensure efficient services.  
**NFR-03**: (Robustness) The system shall handle potential double-taps efficiently and prevent duplicate requests from being created.   
**NFR-04**: (Usability) The system shall ensure simple steps for patients to create refill requests and in a short timeframe.  
**NFR-05**: (Portability) The system shall maintain a responsive design and respond to different screen sizes with no errors.  

## *Student 2 Contributions (Dima)*  
**NFR-06**: (Reliability) The system shall not permit a prescription record to be created with missing required fields leading to incomplete records from entering the system.  
**NFR-07**: (Security) Only users with roles “Doctor” or “Pharmacy Staff” are permitted to create or edit a prescription record.   
**NFR-08**: (Performance) The system shall save a newly created prescription record and make it available for refill requests within 2 seconds.  
**NFR-09**: (Usability) The system shall be able to locate a specific patient's prescription record using a search function.  
**NFR-10**: (Robustness) The system shall reject an attempt to advance a refill request to the next stage out of sequence without crashing or corrupting the request record.  

## *Student 3 Contributions (Maryam)*  
**NFR-11**: (Usability) A new patient shall be able to complete account registration in under 5 minutes without external assistance.    
**NFR-12**: (Reliability) The system shall correctly update inventory counts with 99.9% accuracy after each stock update transaction.  
**NFR-13**: (Performance) Status change notifications shall be delivered to the patient within 30 seconds of pharmacy staff updating the order status.    
**NFR-14**: (Security) Patient registration data shall be stored using encrypted fields for any personally identifiable information.  
**NFR-15**: (Maintainability) The inventory threshold value used for low-stock alerts shall be configurable by pharmacy management without requiring a code change.  

## *Student 4 Contributions (Yuchang)*  
**NFR-16**: (Performance) The system shall display a patient’s active prescription details within 2 seconds after the patient requests them.  
**NFR-17**: (Security) The system shall prevent patients from viewing prescription or refill information belonging to other patients.  
**NFR-18**: (Reliability) The system shall preserve the recorded status and timestamp of a refill request after the system is restarted.  
**NFR-19**: (Usability) The system shall display the current refill request status using clear status labels such as Pending, Approved, Preparing, and Ready for Pickup.  
**NFR-20**: (Auditability) The system shall retain the date, time, and previous status when a refill request status is changed.  
