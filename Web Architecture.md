# Architecture Decision

### Presentation layer includes react and API controller
- React is capable of providing excellent response time and user experience
- Separate frontend and backend development
- Possible to show and update different models in the same form

### Presentation layer is solely responsible to handle request and response, perform authentication
- Different authentication scheme can be applied based on project so it does not go into application or domain layer
- A default identity solution will be implemented but it is optional for the project
- User id instead of user name will be sent to the application layer to avoid user name changes
- User name, profile picture can be included in the ID token for presentation, nothing to do with other layers

### Application layer
- Gather all required domains and perform interactions among different domains
- Application logic and validation will go into this layer
- Authorization will be performed in application layer
- Application can seed initial data, configuration and events into domains to make the domains best fit for the application

### Domain layer
- It contains domain service and domain model
- Domain service interact with domain models and repositories
- Domain model is only responsible for modifying properties of an entity, related entity should be feeded into the method by services
- A domain service can reference other related domain service (e.g. Product service reference product type service. So it does not require application service to handle)

### Entity
- It contains only properties
- It is expected to use with entity framework core. So complex modelling is allowed to take advantage of OOP.
- Fluent API is preferred over data annotation because it can adopt to different databases
- Default database configuration should be prepared
- Default table relation should be optional for different applications

### Unit of work
- It is responsible to store the event, state and changes from domain service and repository
- It manages the connection and transaction

### Entity framework core
- Easy database creation and migration
- Easy switching database store
- It supports complex models which allow easier reuse of class

### Repository
- It is responsible to interact with the unit of work for the changes and get data
- It gives flexibility to use other data access technology for some queries
- It does not have the knowledge of database connection
- Parameterized SQL or stored procedure are allowed for queries
- Feel free to create repository for different use cases, so changing the database stores will be easier
