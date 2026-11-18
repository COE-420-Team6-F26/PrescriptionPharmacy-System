# *Architectural Style Selection:*

## 1. Selected Architectural Style
Layered Architecture (3-Tier Architecture): Presentation Layer, Business Logic Layer, and Data Access Layer.

## 2. Main Characteristics
- **Separation of Concerns:** Each layer has a specific responsibility.
- **Modularity:** System functions are organized into separate components.
- **Controlled Data Access:** The presentation layer interacts with the business logic rather than accessing stored information directly.
- **Maintainability:** Changes within one layer can often be implemented without modifying other layers.
- **Reusability:** Business logic can be reused across different interfaces or system functions.

## 3. Why It Is Appropriate for the Project
The application contains multiple functions that must work together while maintaining clear responsibilities. Patients interact with the system to submit refill requests and view prescription information, while staff manage prescriptions, review refill requests, update inventory, and mark refills as ready for pickup. Separating the user interface, business logic, and data access allows these operations to be organized efficiently.

For example, when pharmacy staff mark a refill as ready for pickup, the presentation layer receives the action, the business layer validates the refill status and coordinates the workflow, and the data access layer stores the updated status, pickup order, and refill history. As a result, this model supports a structured and maintainable system design.

## 4. How It Supports the Design Goals
- **Security (ADG-01):** Authentication, authorization, and access-control rules are enforced within the business layer. Database access is restricted through the data access layer, reducing the risk of unauthorized access to patient and prescription information.
- **Maintainability (ADG-02):** Separating presentation, business logic, and data access makes it easier to modify, test, and maintain individual components without unnecessarily affecting the entire system.

## 5. Advantages and Limitations

| Advantages | Limitations |
|---|---|
| Organized system structure | Communication between layers may introduce additional processing overhead |
| Maintainable | Changes affecting multiple layers may require coordinated modifications |
| Supports controlled access to sensitive data | Poorly defined dependencies between layers reduce maintainability |
| Individual layers and components can be modified independently | A layered architecture does not guarantee security by itself; proper authentication, authorization, and data protection must still be implemented |
| Suitable for systems with database operations and multiple user roles | |