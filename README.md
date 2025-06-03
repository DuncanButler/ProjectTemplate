# .NET Architecture Template

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![.NET](https://img.shields.io/badge/.NET-8.0%20%7C%209.0-blue)
![GitHub Copilot](https://img.shields.io/badge/GitHub%20Copilot-Enabled-brightgreen)

> A professional .NET project template with pre-configured architecture documentation, GitHub Copilot integration, and best practices for modern application development.

## What Is This Template?

This template provides a structured foundation for building well-architected .NET applications with built-in support for:

- **Architecture Documentation** using [Structurizr](https://structurizr.com/)
- **GitHub Copilot** configuration with smart prompts and AI assistance
- **Organized Project Structure** with clear separation of concerns
- **DevOps Pipeline** ready with GitHub Actions workflows
- **Best Practices** for modern .NET development

## Key Features

- ✅ **Pre-configured Architecture** - Architecture-as-Code using Structurizr
- ✅ **Enforced Project Organization** - Standardized directory structure for Source, Tests, and Infrastructure
- ✅ **AI-Assisted Development** - GitHub Copilot integration with specialized prompts
- ✅ **Modern Development Environment** - EditorConfig, DevContainer, and recommended extensions
- ✅ **CI/CD Ready** - GitHub Actions workflows for build and test
- ✅ **Consistency Enforcement** - Centralized build properties and package versioning

## Getting Started

### Installation

Install the template in your .NET environment:

```powershell
# Uninstall any previous versions
dotnet new uninstall {full path to repository}

# Install the template
dotnet new install {full path to repository}
```

### Create a New Project

Generate a new project from the template:

```powershell
dotnet new arch-template -n YourProjectName
```

### Project Structure

Your new project will be created with this organized structure:

```
YourProjectName/
├── Source/                # Application code projects
│   ├── YourProject.Core/  # Core business logic
│   ├── YourProject.API/   # API projects
│   └── ...                # Other application code
│
├── Tests/                 # Test projects
│   ├── YourProject.UnitTests/
│   ├── YourProject.IntegrationTests/
│   └── ...                # Other test projects
│
├── Infrastructure/        # Infrastructure components
│   ├── YourProject.AppHost/        # Aspire host project
│   ├── YourProject.ServiceDefaults/# Service defaults
│   └── ...                # Other infrastructure components
│
├── Architecture/          # Structurizr architecture models
│   ├── configuration.dsl  # Structurizr configuration
│   ├── models.dsl         # System models
│   └── views.dsl          # Architecture views
│
├── Documents/             # Project documentation
│
├── .github/               # GitHub configuration
│   ├── copilot/           # Copilot guidance and prompts
│   │   └── prompts/       # Specialized prompt templates
│   └── workflows/         # CI/CD workflows
│
├── .devcontainer/         # Development container configuration
├── .vscode/               # VS Code settings and recommendations
│
├── ProjectTemplate.sln    # Solution file
├── run_structurizr.ps1    # Script to visualize architecture
├── PROJECT_STRUCTURE.md   # Project structure guidelines
└── [Configuration files]  # Various configuration files for tools and standards
```

## Developer Workflow

This template is designed to support a modern, productive developer workflow. Here's how to make the most of it:

### 1. Initial Setup

After creating your project from the template:

```powershell
# Navigate to your new project
cd YourProjectName

# Open in VS Code with recommended extensions
code .

# Explore the architecture documentation
code ./Architecture/
```

### 2. Adding New Features

When adding new features to your application:

1. **Update Architecture First**
   - Modify the Structurizr models in the Architecture folder
   - Run `./run_structurizr.ps1` to visualize the changes
   - Review and refine the architecture

2. **Follow the Project Structure Convention**
   - Add application code to the `Source/` directory
   - Add test projects to the `Tests/` directory
   - Add infrastructure components to the `Infrastructure/` directory

3. **Leverage GitHub Copilot**
   - Use the prompt templates in `.github/copilot/prompts/`
   - Ask Copilot for guidance on implementing architectural patterns
   - Use Copilot to generate unit tests

4. **Implement Tests**
   - Practice Test-Driven Development (TDD) where appropriate
   - Ensure all new features have corresponding tests
   - Aim for high code coverage

### 3. Continuous Integration

The template includes GitHub Actions workflows that automatically:

- Build your solution
- Run all tests
- Report any failures

Ensure all CI checks pass before merging feature branches.

### 4. Development Best Practices

- **Keep Architecture Updated**: Ensure your code implementation matches the architecture documentation
- **Follow Clean Code Principles**: Use meaningful names, small functions, and proper separation of concerns
- **Use Dependency Injection**: Follow the dependency injection pattern for loosely coupled components
- **Documentation**: Document public APIs and complex logic

## GitHub Copilot Integration

This template comes with pre-configured GitHub Copilot support to accelerate development:

### Getting Started with Copilot

1. When opening the project in VS Code, Copilot Chat should automatically activate.
2. If not, you can open it manually:
   - Use the shortcut: `Ctrl+Alt+C` (Windows/Linux) or `Cmd+Option+C` (Mac)
   - Or click the Copilot Chat icon in the sidebar

### Using Copilot Chat

Copilot understands your project structure and can help with various tasks:

- **Architecture Questions**: `@workspace How does the architecture of this application work?`
- **Code Generation**: `@workspace Create a new service for user authentication`
- **Project Structure**: `@workspace Where should I add a new API controller?`
- **Debug Assistance**: `@vscode Why is this test failing?`
- **Terminal Commands**: `@terminal How do I run the architecture visualization?`

### Specialized Prompt Templates

This template includes ready-to-use prompt templates in `.github/copilot/prompts/` designed specifically for:

- **Code Generation** - Creating components that follow your architecture
- **Testing** - Generating comprehensive test cases
- **Documentation** - Creating consistent documentation
- **Refactoring** - Improving code quality while preserving behavior
- **API Design** - Creating RESTful API endpoints following best practices
- **Project Setup** - Configuring new features and services

#### How to Use the Prompts

1. Open GitHub Copilot Chat in VS Code
2. Browse the prompt templates in `.github/copilot/prompts/`
3. Copy a prompt that matches your current task
4. Paste it into Copilot Chat and replace placeholders
5. Use the generated code or guidance

## Additional Features

The template includes several additional features to enhance developer productivity:

### Development Environment
- **EditorConfig**: Ensures consistent code style across different editors
- **DevContainer**: Ready-to-use development container configuration for VS Code
- **VS Code Extensions**: Recommended extensions pre-configured

### Build and Configuration
- **Directory.Build.props**: Common build properties for all projects
- **Directory.Packages.props**: Centralized package version management
- **Global.json**: SDK version control
- **CI/CD Workflows**: GitHub Actions workflows for building and testing

### Templates and Guidelines
- **Docker Support**: Dockerfile template for containerization
- **Contributing Guidelines**: Instructions for project contribution
- **Project Structure**: Clear organization of source code, tests, and infrastructure

### Best Practices
- Code style enforcement
- Centralized dependency management
- Consistent environment setup
- Automated testing configurations

## Architecture Documentation

One of the key features of this template is the built-in architecture documentation using Structurizr.

### What is Structurizr?

[Structurizr](https://structurizr.com/) is a tool for creating software architecture diagrams and documentation based on the C4 model. It allows you to:

- Define your architecture as code (Architecture-as-Code)
- Generate consistent diagrams at different levels of abstraction
- Keep documentation and implementation in sync

### Exploring the Architecture

The template includes a pre-configured architecture model in the `Architecture/` directory:

- `configuration.dsl` - Structurizr workspace configuration
- `models.dsl` - Definition of systems, containers, and components
- `views.dsl` - Various views of the architecture

To visualize the architecture:

```powershell
# Run the Structurizr script
./run_structurizr.ps1

# Open the generated diagrams in your browser
```

### Evolving the Architecture

As your application evolves, update the architecture models to reflect the changes:

1. Modify the DSL files in the `Architecture/` directory
2. Run the visualization script
3. Review and refine the architecture
4. Ensure your implementation matches the architecture

## Build Configuration Files

This template includes two important MSBuild configuration files:

### Directory.Build.props

`Directory.Build.props` centralizes common project settings and build properties. It provides:

- Consistent settings across all projects in your solution
- Single place to manage common properties
- Enforcement of team coding standards

To customize:
- Edit the file to adjust settings for your team's preferences
- Add additional properties as needed for your project

### Directory.Packages.props

`Directory.Packages.props` enables Central Package Management (CPM) to maintain consistent package versions across your solution. Benefits include:

- Eliminate version conflicts between projects
- Simplify dependency updates
- Ensure consistent dependencies

To use CPM effectively:
1. Define package versions in `Directory.Packages.props`
2. In .csproj files, reference packages without version numbers: `<PackageReference Include="PackageName" />`
3. All projects will use the versions defined centrally

Learn more about [Central Package Management](https://learn.microsoft.com/en-us/nuget/consume-packages/central-package-management).

## Contribution and Support

### Contributing

We welcome contributions to improve this template! Please see the [CONTRIBUTING.md](CONTRIBUTING.md) file for guidelines.

### License

This template is available under the MIT License. See the LICENSE file for more information.

### Support

If you encounter any issues or have questions about this template, please [open an issue](https://github.com/yourusername/yourrepositoryname/issues) on GitHub.
