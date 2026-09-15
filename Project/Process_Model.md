# *Software Process Model:*

## Selected Model
For our Prescription Refill and Pharmacy Pickup System, we selected the **Incremental Model** as the most appropriate software process model. The system is built in a number of smaller steps, each of which adds a set of functional characteristics. This approach is appropriate for our project because it has multiple related functions that may be developed independently.

## Justification
The Incremental Model is suited for our project since the system includes multiple modules which are:
- Prescription Management
- Medication Management 
- Patient Information
- Pharmacy pickup  

Each of which can be created separately. Each feature can be built and evaluated in stages before being merged into the rest of the system. This model also allows changes to requirements, since new requirements or improvements identified during development can be added to later increments. In addition, the Incremental Model suits our small development team, since members can work on different modules while coordinating their work through the shared GitHub repository.

## Overheads / Drawbacks & How We Will Manage Them
**Drawback 1**: Integration problems when combining modules  
*How We Will Manage It*: Set up the database and system structure early, and test modules regularly against it

**Drawback 2**: Testing takes more time, since each increment needs its own testing  
*How We Will Manage It*: Test each feature as it is developed, and perform integration testing when combining modules

**Drawback 3**: Team coordination can be difficult across increments  
*How We Will Manage It*: Divide work clearly, communicate regularly, and use GitHub branches to avoid conflicts
