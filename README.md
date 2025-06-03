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

### Project Structure
The template enforces a specific project structure that Copilot is configured to understand:
- `Source/` - Contains all application code and business logic
- `Tests/` - Contains all test projects with the `.Tests` suffix
- `Infrastructure/` - Contains Aspire host projects and service defaults
