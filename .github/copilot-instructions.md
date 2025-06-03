# Best Practices for .NET C# Projects using Blazor, Aspire, and PostgreSQL

## Project Structure
- Follow the predefined directory structure of the template:
  - `Source/`: Contains all application code and business logic
    - Name projects according to their purpose: `ProjectName.Core`, `ProjectName.API`, etc.
  - `Tests/`: Contains all test projects
    - Use naming convention: `ProjectName.UnitTests`, `ProjectName.IntegrationTests`
  - `Infrastructure/`: Contains all infrastructure components
    - Place Aspire host projects here with naming convention: `ProjectName.AppHost`
    - Place service defaults here with naming convention: `ProjectName.ServiceDefaults`
  - `Architecture/`: Contains Structurizr architecture models
  - `Documents/`: Contains project documentation
- Keep architecture documentation synchronized with code implementation
- Use feature folders within projects for better organization
- Group related functionality together rather than by technical type

## Blazor
- Prefer component-based architecture; keep components small and reusable.
- Use dependency injection for services.
- Avoid business logic in UI components; delegate to services.
- Use `@code` blocks for logic, not inline in markup.
- Implement proper state management (e.g., cascading parameters, state containers).

## Aspire (Cloud-Native .NET)
- Place Aspire host projects in the `Infrastructure/` directory with naming convention: `ProjectName.AppHost`
- Place service defaults projects in the `Infrastructure/` directory with naming convention: `ProjectName.ServiceDefaults`
- Use Aspire for distributed application orchestration and service discovery
- Define clear contracts between microservices
- Use health checks and telemetry for monitoring
- Secure service-to-service communication (e.g., mTLS, OAuth)
- Use configuration providers for environment-specific settings

## PostgreSQL
- Use Entity Framework Core or Dapper for data access.
- Use migrations for schema changes (`dotnet ef migrations`).
- Store connection strings securely (e.g., environment variables, Azure Key Vault).
- Use parameterized queries to prevent SQL injection.
- Optimize queries and use indexes appropriately.

## General .NET Practices
- Use async/await for I/O operations
- Avoid mixing synchronous and asynchronous code
- Choose appropriate collection types based on access patterns
- Implement IDisposable and IAsyncDisposable correctly for resource cleanup
- Use dependency injection for loose coupling and testability
- Apply SOLID principles in class design
- Leverage .NET's built-in middleware pipelines for cross-cutting concerns
- Prefer configuration over hardcoding (use IOptions pattern)
- Use strongly-typed settings with IOptions<T>
- Follow the options validation pattern for configuration
- Implement proper logging with structured data
- Use LoggerMessage source generators for high-performance logging
- Implement health checks for services and dependencies
- Use metrics collection for monitoring and alerting

## Security
- Use ASP.NET Core Identity or external providers for authentication
- Implement proper authorization with policies and requirements
- Apply the principle of least privilege for all operations
- Validate and sanitize all user inputs
- Implement proper CORS policies to prevent cross-site attacks
- Use anti-forgery tokens for forms and AJAX requests
- Secure sensitive data both in transit and at rest
- Use HTTPS everywhere with proper certificate management
- Implement proper secrets management (Azure Key Vault, etc.)
- Follow security headers best practices (HSTS, CSP, etc.)
- Regularly update dependencies and monitor for vulnerabilities
- Implement rate limiting for publicly exposed endpoints
- Use secure defaults and fail securely

## DevOps & CI/CD
- Use GitHub Actions or Azure DevOps for automated builds and deployments
- Implement branch protection and pull request workflows
- Run tests, static analysis, and security scanning in CI pipelines
- Use Docker for containerization with multi-stage builds for small images
- Define services in `docker-compose` or Aspire manifests
- Follow infrastructure-as-code principles for deployment environments
- Implement blue/green or canary deployment strategies
- Automate database migrations safely during deployment
- Set up monitoring and alerting for production environments
- Implement proper logging and telemetry collection
- Create disaster recovery plans and test them regularly

## Documentation
- Document APIs with Swagger/OpenAPI following best practices
- Use XML comments for public APIs and generate documentation from them
- Maintain comprehensive architecture diagrams with C4 model
- Document architectural decisions with Architecture Decision Records (ADRs)
- Create onboarding documentation for new team members
- Provide usage examples and sample code for libraries
- Keep documentation in sync with code changes
- Document configuration options and environment variables

## Performance & Scalability
- Use caching appropriately with proper invalidation strategies (MemoryCache, Redis)
- Implement efficient data access patterns (e.g., asynchronous streaming for large datasets)
- Use pagination for large result sets
- Consider using background processing for CPU-intensive tasks
- Implement circuit breakers and bulkheads for resilience
- Design for horizontal scaling from the start
- Use message queues to decouple services and handle load spikes
- Optimize database queries with proper indexes and execution plans
- Consider NoSQL databases for specific performance scenarios
- Use performance benchmarking tools to identify bottlenecks
- Implement resource pooling for expensive resources
- Consider read/write splitting for high-traffic applications
- Use compression for API responses
- Implement proper connection handling and connection pooling

## C# Best Practices

### Code Style & Conventions
- Follow Microsoft's C# coding conventions and .NET design guidelines
- Use meaningful, descriptive names for variables, methods, and classes
- Prefer explicit type declarations (`var` only when type is obvious)
- Use PascalCase for public members, camelCase for parameters and local variables
- Prefix private fields with underscore (`_privateField`)
- Use nullable reference types and non-nullable by default
- Place using directives at the top of the file, not inside namespaces

### Modern C# Features
- Use pattern matching where appropriate (switch expressions, property patterns)
- Leverage language features like init-only properties, records, and top-level statements
- Use expression-bodied members for concise one-liners
- Utilize collection expressions and list patterns for more readable code
- Consider using primary constructors for simple classes
- Use required properties for mandatory initialization

### Classes & Types
- Keep classes focused on a single responsibility (SRP)
- Prefer composition over inheritance
- Make classes either a service, entity, value object, or DTO - avoid mixing concerns
- Use interfaces to define contracts between components
- Consider using records for immutable data objects
- Make classes sealed by default unless designed for inheritance
- Minimize class visibility (internal by default, public only when necessary)

### Methods & Functions
- Keep methods short and focused on a single task
- Limit parameter count (≤ 3 parameters ideally)
- Return early from methods to avoid deep nesting
- Avoid output/ref parameters when possible
- Use method groups when passing methods as delegates
- Return Task/ValueTask for asynchronous methods
- Use cancellation tokens for cancelable operations

### Error Handling
- Use exceptions for exceptional conditions, not for control flow
- Create custom exception types for specific error scenarios
- Prefer validation at the entry points of public APIs
- Use Result pattern for expected failures rather than throwing exceptions
- Always catch specific exceptions, not Exception (except at top-level boundaries)
- Include contextual information in exception messages

### Performance Considerations
- Use spans and memory for high-performance string and array operations
- Consider using ArrayPool for frequent array allocations
- Avoid unnecessary boxing and unboxing
- Minimize LINQ in performance-critical paths
- Use efficient collection types for specific scenarios (Dictionary vs List)
- Use value types and ref returns/locals where appropriate for performance
- Consider using ReadOnlySpan<char> instead of string for parsing operations

---
Following these practices will help ensure your .NET Blazor project with Aspire and PostgreSQL is maintainable, secure, and scalable.