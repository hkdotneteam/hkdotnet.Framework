# hkdotnet.Framework
The shared components to build a web backend

The following components are expected to be developed
1. User and authentication (or ASP.Net Identity Core)
3. Roles and permissions (open for application to define)
4. Event broker (synchronous and asynchronous events)
5. Notification subscription (open for application to define and user to subscribe)
6. User notification hub (show and read notification)
7. Dashboard (Widget shows in main page, open for application to define and user to subscribe)
8. Email template and sender (open for application to define the email template schema and for user to change the template, set the sender and SMTP/Gmail/Outlook)
9. Global search (Open for application to return result if a user search globally)
10. Private message box (for internal communication)
11. User state (a generic table to store status or preference for a user)
12. Application setting (a generic table to store the configuration where user can modify, application can define the setting with default value)
13. Shortcuts (Application can define shortcuts and user can manage own shortcuts for easy access)
14. Audit trail

Each domain should contain the following components:
1. Entities/Aggregate root
2. Domain model
3. Domain configuration (if any)
4. Domain service with interface
5. Repository interface
6. Default db configuration (for EF core)
7. Event handlers and arguments
8. Specific exceptions (if any)

The following items are required for the architecture.
1. Entity (Id), Aggregate root (Id, Created, LastUpdated, RowVersion)
2. Common entity or data object
3. Domain model: Sole class to modify states of an entity, domain configuration will be passed into each model
4. Domain configuration: A class to define common configuration (by application or by user)
5. Domain service: Interact with domain model and repository, model validation, event triggers
6. Unit of work: Manage connection and transaction, store and save the changes and asynchronous events after submission
7. Repository: (Use EF core) Generic repository to interact with unit of work to make changes
8. DbContext: Define an interface to modularize the DbContext
9. Application service or commands: Common task to do in application service (e.g. authorization, model validation)
10. Command handler: To store, execute or rollback commands
11. Utilities or helper classes for different layers

Patterns and development stacks summary:
- Domain driven
- Event driven
- Test driven
- Repository and unit of work pattern
- Entity framework core (Postgresql by default)
- Code first approach
- .NET 6
- ASP.Net Core with react
- Reporting: Fast report?
- Visual studio or VS code
- Flexible deployment (App service, Windows/Linux VMs, Docker)
- Github for source control

For scaling
- Redis (for caching management)
- RabbitMQ (for storing and firing async event)
