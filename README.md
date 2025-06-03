# Project Template

## Introduction
This repository presents a basic project template for a dot net project

## Dot Net Solution

The repository contains a dot net solution, that has no current projects added, projects are stored in the source directory, along with tests in the tests directory.

When using the aspire project templates it is recommended that the host and service default projects are added to the infrastructure folder

## Architecture

The default template has a basic architecture for a website with a user, service layer and database built in the architecture folder using [Structurizr](https://structurizr.com/)


## Instalation
run the following command from the root of the coloned repository, to uninstall any previous versions of the template and install the new verson:

```
dotnet new uninstall {full path to repository}

dotnet new install {full path to repository}
```

## Usage
To create a new project using this template, run the following command:

```   
dotnet new arch-template -n {project name}
```

## GitHub Copilot Integration

This project is configured to use GitHub Copilot in Chat mode by default:

1. When opening the project in VS Code, Copilot Chat should automatically activate.
2. If not, you can open it manually:
   - Use the shortcut: `Ctrl+Alt+C` (Windows/Linux) or `Cmd+Option+C` (Mac)
   - Or click the Copilot Chat icon in the sidebar

### Using Copilot Chat
- Ask questions about the codebase with `@workspace`
- Generate new code with detailed prompts
- Debug issues with `@vscode`
- Get terminal help with `@terminal`

### Prompt Templates
This project includes ready-to-use prompt templates to help you get the most out of GitHub Copilot. You'll find them in the `.github/copilot/prompts/` directory.

#### How to Use the Prompts
1. Open GitHub Copilot Chat in VS Code
2. Copy a prompt from one of the prompt template files
3. Paste it into the chat
4. Replace the placeholders (text in [brackets]) with your specific needs
5. Send the prompt

#### Available Prompt Categories
- **Code Generation** - Create new code components quickly
- **Testing** - Generate comprehensive test cases
- **Documentation** - Create documentation for your code
- **Refactoring** - Improve existing code
- **API Design** - Design RESTful API endpoints
- **Project Setup** - Configure services and middleware

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

## Build Configuration Files

This template includes two important MSBuild configuration files that are considered best practices for modern .NET development:

### Directory.Build.props

`Directory.Build.props` centralizes common project settings and build properties. While not strictly required, it provides:

- Consistent settings across all projects in your solution
- Single place to manage common properties
- Enforcement of team coding standards

You can modify or remove this file if it doesn't fit your workflow.

### Directory.Packages.props

`Directory.Packages.props` enables Central Package Management (CPM) to maintain consistent package versions across your solution. Benefits include:

- Eliminate version conflicts between projects
- Simplify dependency updates
- Ensure consistent dependencies

CPM is optional but highly recommended for multi-project solutions.

To use:
1. Define package versions in `Directory.Packages.props`
2. In .csproj files, reference packages without version numbers: `<PackageReference Include="PackageName" />`
3. All projects will use the versions defined centrally

Learn more about [Central Package Management](https://learn.microsoft.com/en-us/nuget/consume-packages/central-package-management).
