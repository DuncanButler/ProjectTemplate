# Project Structure Guidelines

This project follows a specific structure to organize code effectively:

## Directory Organization

```
ProjectName/
├── Source/                # Main source code
│   ├── ProjectName.Core/  # Core business logic
│   ├── ProjectName.API/   # API projects
│   └── ...                # Other application code
│
├── Tests/                 # All test projects
│   ├── ProjectName.UnitTests/
│   ├── ProjectName.IntegrationTests/
│   └── ...                # Other test projects
│
└── Infrastructure/        # Infrastructure components
    ├── ProjectName.AppHost/          # Aspire host project
    ├── ProjectName.ServiceDefaults/  # Service defaults
    └── ...                # Other infrastructure components
```

## Project Type Guidelines

- **Test Projects**: All projects containing tests (unit, integration, etc.) should be placed in the `Tests` directory and follow the naming convention `*.Tests.csproj`
  
- **Aspire Projects**: All Aspire host projects should be placed in the `Infrastructure` directory and follow the naming convention `*.AppHost.csproj`
  
- **Service Defaults**: All service defaults projects should be placed in the `Infrastructure` directory and follow the naming convention `*.ServiceDefaults.csproj`
  
- **Application Code**: All other projects containing application code should be placed in the `Source` directory

Please follow these conventions when adding new projects to maintain a consistent structure.
