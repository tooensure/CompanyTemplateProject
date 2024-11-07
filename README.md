
# Company Template Project

Structured repository for managing business documentation, project management, branding, and operations with modular templates.

## Table of Contents

- [Project Overview](#project-overview)
- [Folder Structure](#folder-structure)
- [Project Phases](#project-phases)
- [Deployment Guide](#deployment-guide)
- [Coding Conventions and Standards](#coding-conventions-and-standards)
- [Specifications List](#specifications-list)
- [Testing and Quality Assurance](#testing-and-quality-assurance)
- [Additional Resources](#additional-resources)
- [License](#license)
- [Contributing](#contributing)
- [Project Roadmap](#project-roadmap)
- [FAQ](#faq)

## Project Overview

This project serves as a foundation for developing cloud-native applications, enabling both web and native platforms. It includes:

- **.NET MAUI App**: A cross-platform application for mobile and desktop.
- **Blazor WebAssembly App**: A web-based companion app that serves as interactive documentation and a web interface for the project.
- **AI Semantic Kernel**: Provides AI-driven NLP capabilities.
- **Redis Caching**: Enhances performance through caching and real-time data storage.
- **Aspire Framework**: Supports modular and scalable services architecture.

## Folder Structure

```plaintext
CompanyTemplateProject/
├── src/                              # All source code and project modules
│   ├── Core/                         # Core services, policies, and management modules
│   │   ├── Policies/                 # Organizational policies and compliance templates
│   │   ├── Management/               # Company management modules
│   │   ├── Services/                 # Aspire service modules
│   │   ├── AI/                       # AI Semantic Kernel and related services
│   │   └── Caching/                  # Redis caching services
│   └── Infrastructure/               # Infrastructure configurations (e.g., appsettings.json)
│   ├── Website/                      # Blazor WebAssembly frontend for web documentation
│   └── MauiApp/                      # .NET MAUI app for mobile/desktop platforms
├── Documentation/                    # Documentation files for the project
├── LICENSE
└── README.md
```

## Project Phases

1. **Phase 1**: Initial Setup and Core Module Development.
2. **Phase 2**: AI Integration with Semantic Kernel.
3. **Phase 3**: Redis Caching Implementation.
4. **Phase 4**: Policy and Compliance Documentation.
5. **Phase 5**: Management Modules (User, Employee, Project).
6. **Phase 6**: Frontend Development and API Communication.
7. **Phase 7**: Testing, CI/CD, and Deployment.

## Deployment Guide

### Blazor WebAssembly Deployment to GitHub Pages

1. **Set Output Path**: Configure `OutputPath` in `Website/src/CompanyTemplateProject.csproj` to `/docs`.
2. **Build the Project**:
   ```bash
   cd Website/src
   dotnet publish -c Release -o ../docs
   ```
3. **Configure GitHub Pages**:
   - Go to **Settings > Pages**.
   - Set **Source** to `main` branch and **Folder** to `/docs`.
4. **Automate Deployment** (Optional):
   - Use GitHub Actions for automated deployment to GitHub Pages. See `.github/workflows/deploy.yml`.

### .NET MAUI App Distribution via GitHub Releases

1. **Build .NET MAUI for Each Platform**:
   - Compile the app for each platform (e.g., Android, iOS, Windows).
2. **Create a GitHub Release**:
   - Upload compiled binaries (e.g., `.apk`, `.app`, `.exe`) to **Releases**.
3. **Automate with GitHub Actions** (Optional):
   - Set up GitHub Actions to build and publish releases on tag pushes. See `.github/workflows/release.yml`.

## Coding Conventions and Standards

- **Naming Conventions**: PascalCase for classes and methods, camelCase for fields and parameters.
- **Dependency Injection**: Configured in `Program.cs` and `Startup.cs`.
- **Configuration Management**: Centralized in `appsettings.json`.
- **Documentation Standards**: Use AsciiDoc for structured documentation.

## Specifications List

Each module or component has a specification document, following best practices in modular documentation. Key specifications include:

- **SPEC-CORE-001**: Company Service (`company_service.adoc`)
- **SPEC-AI-001**: Semantic Kernel Service (`semantic_kernel_service.adoc`)
- **SPEC-CACHE-001**: Redis Cache Service (`redis_cache_service.adoc`)
- **SPEC-WEB-001**: Website Structure and Components (`website_structure_components.adoc`)
- **SPEC-DEPLOY-002**: Deployment Guide for GitHub Pages and GitHub Releases (`deployment_github_pages.adoc`)

Refer to `Project_Phases_and_Specifications.adoc` for the complete list.

## Testing and Quality Assurance

- **Unit Tests**: Defined for core services and modules.
- **Integration Tests**: Configured for end-to-end testing across services.
- **CI/CD**: GitHub Actions are configured for automated builds, testing, and deployments.

## Additional Resources

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Aspire Framework](https://github.com/dotnet/aspire)
- [AI Semantic Kernel Documentation](https://learn.microsoft.com/en-us/semantic-kernel)
- [Redis Documentation](https://redis.io/documentation)
- [.NET MAUI Documentation](https://docs.microsoft.com/en-us/dotnet/maui/what-is-maui)
- [Blazor WebAssembly Documentation](https://docs.microsoft.com/en-us/aspnet/core/blazor/?view=aspnetcore-7.0)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

We welcome contributions to improve and extend the **Company Template Project**. To contribute:

1. **Fork the repository** and create your feature branch from `main`.
2. **Make your changes** following the coding conventions and standards outlined in this README.
3. **Submit a pull request** with a clear description of your changes, referencing any related specifications or issues.

### Contribution Guidelines

- **Coding Standards**: Follow the project's naming conventions, structure, and best practices to maintain consistency.
- **Documentation**: Ensure any new features or changes are documented in the relevant `.adoc` files, especially if they affect core modules, the Blazor WebAssembly frontend, or .NET MAUI functionality.
- **Testing**: Add unit tests for any new services, and update integration tests if your changes affect multiple components.

For more details, please see the `CONTRIBUTING.md` file.

## Project Roadmap

The project roadmap outlines planned features and improvements:

- **Enhanced AI Capabilities**: Extend the AI Semantic Kernel to support additional NLP functions.
- **Role-Based Access Control**: Improve the User Management module with more granular permissions.
- **Cross-Platform Integrations**: Enhance interoperability between the .NET MAUI and Blazor WebAssembly components for seamless data sharing.
- **Improved CI/CD Pipelines**: Expand CI/CD workflows to automate release versioning and deployment.

For a detailed roadmap and milestones, refer to `Project_Phases_and_Specifications.adoc`.

## FAQ

### Why use both .NET MAUI and Blazor WebAssembly?

.NET MAUI is ideal for creating native mobile and desktop applications, while Blazor WebAssembly provides a lightweight, web-based companion app. This combination allows us to deliver cross-platform functionality with native performance for mobile/desktop users and a web interface for documentation or limited interactions.

### How does Redis improve application performance?

Redis caching is used to store frequently accessed data, reducing the load on backend services. By caching data, we can serve user requests faster, making the application more responsive.

### Can I customize the Blazor WebAssembly app?

Yes, the Blazor WebAssembly app is structured to allow customization. You can add new interactive components, connect additional APIs, and adjust the styling to align with your project's branding or functionality requirements.
