
# Company Template Project - Folder Structure

The **Company Template Project** is structured to support both native and web-based platforms, leveraging .NET MAUI, Blazor WebAssembly, Redis caching, AI Semantic Kernel, and the Aspire Framework. This document provides an overview of the folder structure and organization of the project files, with all source code organized under the `src/` folder for enhanced clarity and maintainability.

---

## Folder Structure Overview

```plaintext
CompanyTemplateProject/
├── src/                              # All source code and project modules
│   ├── Core/                         # Core services, policies, and management modules
│   │   ├── Policies/                 # Organizational policies and compliance templates
│   │   │   ├── privacy_policy.adoc   # Privacy Policy template
│   │   │   ├── terms_of_service.adoc # Terms of Service template
│   │   │   └── code_of_conduct.md    # Code of Conduct
│   │   ├── Management/               # Company management modules
│   │   │   ├── UserManagement/       # Role-based access and permissions
│   │   │   ├── EmployeeManagement/   # Employee details, roles, and departments
│   │   │   └── ProjectManagement/    # Project tracking and task management
│   │   ├── Services/                 # Aspire service modules
│   │   │   ├── Company/              # CompanyService module (example)
│   │   │   ├── Product/              # ProductService module (example)
│   │   │   └── Shared/               # Shared models and utilities for services
│   │   ├── AI/                       # AI Semantic Kernel and related services
│   │   │   ├── SemanticKernelService/# Service layer for AI SK operations
│   │   │   ├── Models/               # Models for AI requests and responses
│   │   │   └── Prompts/              # NLP prompts for AI processing tasks
│   │   └── Caching/                  # Redis caching services
│   │       ├── RedisCacheService/    # Redis service layer for caching
│   │       ├── Models/               # Data models for cached objects
│   │       └── Helpers/              # Utility classes for cache operations
│   └── Infrastructure/               # Infrastructure configurations
│       ├── appsettings.json          # Centralized configuration file
│       ├── Program.cs                # Main entry point for DI and app setup
│       └── Startup.cs                # Configure services, middlewares, and DI
│   ├── Website/                      # Blazor WebAssembly frontend for web documentation
│   │   ├── src/                      # Source files for Blazor WebAssembly
│   │   ├── wwwroot/                  # Static assets for Blazor (CSS, JS, images)
│   │   ├── docs/                     # Output folder for GitHub Pages deployment
│   │   └── README.md                     
│   └── MauiApp/                      # .NET MAUI app for mobile/desktop platforms
│       ├── Platforms/                # Platform-specific code for Android, iOS, etc.
│       ├── Resources/                # Shared resources, images, and fonts for MAUI
│       ├── Views/                    # Views for .NET MAUI UI
│       ├── Models/                   # Data models for .NET MAUI app
│       └── ViewModels/               # ViewModels for .NET MAUI (MVVM pattern)
│       └── README.md                     
├── Documentation/                    # Documentation files for the project
│   ├── Project_Phases_and_Specifications.adoc # High-level project overview and SPEC list
│   ├── deployment_github_pages.adoc  # Guide for deploying Blazor WebAssembly to GitHub Pages
│   ├── setup_installation.adoc       # Setup and installation guide for the project
│   └── README.md
├── LICENSE
└── README.md
```

---

## Folder Breakdown

- **src/**: Contains all source code, including .NET MAUI and Blazor WebAssembly projects, along with core services, AI modules, Redis caching, and infrastructure files. This folder consolidates all code, maintaining a clean root directory.

- **src/Core/**: Contains the core business logic, policies, AI capabilities, Redis caching, and management modules.

- **src/Infrastructure/**: Holds application settings, configuration files, and dependency injection setups, including `appsettings.json`, `Program.cs`, and `Startup.cs`.

- **src/Website/**: Houses the Blazor WebAssembly app, serving as the web documentation and companion frontend. The `/docs` folder is used for GitHub Pages output.

- **src/MauiApp/**: Contains the .NET MAUI app files for mobile and desktop, including platform-specific code, views, and MVVM structure.

- **Documentation/**: A dedicated folder for project documentation in AsciiDoc and Markdown format. This includes high-level overviews, phase specifications, deployment guides, and installation instructions.

---

This folder structure organizes the project with clear separation between source code, supporting documentation, and configuration files, streamlining development and deployment.
