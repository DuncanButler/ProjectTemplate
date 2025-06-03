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
- Use async/await for I/O operations.
- Write unit and integration tests; use test projects.
- Apply SOLID principles and clean code practices.
- Use logging (e.g., Serilog) and structured logs.
- Handle exceptions gracefully and provide user-friendly error messages.

## Security
- Use ASP.NET Core Identity or external providers for authentication.
- Validate and sanitize all user inputs.
- Use HTTPS everywhere.
- Regularly update dependencies and monitor for vulnerabilities.

## DevOps & CI/CD
- Use GitHub Actions or Azure DevOps for automated builds and deployments.
- Run tests and static analysis in CI pipelines.
- Use Docker for containerization; define services in `docker-compose` or Aspire manifests.
- Automate database migrations during deployment.

## Documentation
- Document APIs with Swagger/OpenAPI.
- Use XML comments for public APIs.
- Maintain a clear README and architecture diagrams.

## Performance & Scalability
- Use caching where appropriate (e.g., MemoryCache, Redis).
- Profile and monitor application performance.
- Scale services horizontally as needed.

---
Following these practices will help ensure your .NET Blazor project with Aspire and PostgreSQL is maintainable, secure, and scalable.