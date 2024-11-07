# Company Template Project

The **Company Template Project** is a modular, cloud-ready .NET solution designed for developing business applications with best practices in architecture, coding conventions, and documentation. This project leverages **.NET 9.0**, **C# 10+** features, and integrates the **Aspire Framework** for modular services, **AI Semantic Kernel** for intelligent data processing, **Redis** for caching and real-time data storage, and a **Blazor WebAssembly** frontend. It also includes policies and management modules for operational and organizational support.

---

## Project Overview

This project serves as a foundation for building cloud-native applications, providing tools for managing company documentation, compliance policies, operational modules, AI-driven processing, and caching through Redis. The **Company Template Project** is structured to support modular services, AI-powered interactions, Redis caching, and scalable deployment.

---

## Folder Structure

```plaintext
CompanyTemplateProject/
├── Core/                             # Core services, policies, and management modules
│   ├── Policies/                     # Organizational policies and compliance templates
│   │   ├── privacy_policy.adoc       # Privacy Policy template
│   │   ├── terms_of_service.adoc     # Terms of Service template
│   │   └── code_of_conduct.md        # Code of Conduct
│   ├── Management/                   # Company management modules
│   │   ├── UserManagement/           # Role-based access and permissions
│   │   ├── EmployeeManagement/       # Employee details, roles, and departments
│   │   └── ProjectManagement/        # Project tracking and task management
│   ├── Services/                     # Aspire service modules
│   │   ├── Company/                  # CompanyService module (example)
│   │   ├── Product/                  # ProductService module (example)
│   │   └── Shared/                   # Shared models and utilities for services
│   ├── AI/                           # AI Semantic Kernel and related services
│   │   ├── SemanticKernelService/    # Service layer for AI SK operations
│   │   ├── Models/                   # Models for AI requests and responses
│   │   └── Prompts/                  # NLP prompts for AI processing tasks
│   └── Caching/                      # Redis caching services
│       ├── RedisCacheService/        # Redis service layer for caching
│       ├── Models/                   # Data models for cached objects
│       └── Helpers/                  # Utility classes for cache operations
│   └── README.md
├── Infrastructure/                   # Infrastructure configurations (e.g., appsettings.json)
│   ├── appsettings.json              # Centralized configuration file
│   ├── Program.cs                    # Main entry point for DI and app setup
│   └── Startup.cs                    # Configure services, middlewares
├── Website/                          # Blazor WebAssembly frontend
│   ├── src/                          
│   ├── wwwroot/                      
│   ├── docs/                         
│   └── README.md                     
├── LICENSE
└── README.md
```

- **Core**: Contains business logic, services, policies, management modules, AI processing, and Redis caching.
- **Infrastructure**: Houses application settings, configuration files, and dependency injection setup.
- **Website**: A Blazor WebAssembly app for frontend deployment, including static files for GitHub Pages.

---

## Modules and Purpose

### Redis Caching

The **Redis Caching** module enhances application performance by caching frequently accessed data, reducing load on the database, and supporting real-time data operations. Redis can also be used for caching AI model results, session data, and other data to improve response times.

- **RedisCacheService** (`Caching/RedisCacheService/`): A service layer that handles interactions with Redis for caching data.
- **Models** (`Caching/Models/`): Data models representing objects stored in the cache.
- **Helpers** (`Caching/Helpers/`): Utility classes for cache management, such as setting expiration policies or managing cache keys.

### AI Semantic Kernel (AI SK)

The **AI Semantic Kernel** module provides capabilities for natural language processing, intelligent data retrieval, and user interaction. This module leverages AI SK to enhance application functionality with tasks such as generating responses, extracting information, and handling user queries.

- **SemanticKernelService** (`AI/SemanticKernelService/`): Contains service classes that handle interactions with AI SK.
- **Models** (`AI/Models/`): Defines data models for request and response handling in AI operations.
- **Prompts** (`AI/Prompts/`): Stores reusable NLP prompts for different AI processing tasks, enabling intelligent responses to user requests.

### Policies and Management Modules

The **Policies** and **Management** folders contain templates and modules for operational guidelines and user management, detailed in previous sections.

### Services

The **Services** folder contains Aspire-based services that implement core business logic, such as `CompanyService` and `ProductService`.

---

## Setup Instructions

### Prerequisites

- **.NET 9.0 SDK**: Ensure that .NET 9.0 SDK is installed.
- **Blazor WebAssembly**: Required for building the frontend.
- **AI Semantic Kernel SDK**: Required for AI-related services.
- **Redis**: Install Redis locally or use a managed Redis service (e.g., Azure Cache for Redis).
- **Git**: For version control and pushing changes to GitHub.

### Build and Run

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/CompanyTemplateProject.git
   cd CompanyTemplateProject
   ```

2. **Configure Application Settings**:
   Modify `appsettings.json` in the `Infrastructure/` folder to reflect your environment configurations, including Redis and AI SK settings.

   Example Redis configuration:
   ```json
   {
     "Redis": {
       "ConnectionString": "localhost:6379",
       "DefaultCacheDurationSeconds": 3600
     }
   }
   ```

3. **Install Redis Dependencies**:
   If not already included, install the `StackExchange.Redis` NuGet package for Redis support:
   ```bash
   dotnet add Caching/RedisCacheService package StackExchange.Redis
   ```

4. **Build and Run the Backend**:
   Navigate to the `Core/` directory and run:
   ```bash
   dotnet build
   dotnet run
   ```

5. **Build the Blazor WebAssembly App**:
   Go to the `Website/` folder and publish to the `docs` directory for GitHub Pages:
   ```bash
   dotnet publish -c Release -o docs
   ```

6. **Deploy to GitHub Pages**:
   Push the changes to GitHub and set up GitHub Pages to serve from the `docs` folder on the `main` branch.

---

## Redis Usage

The **RedisCacheService** provides methods for setting, getting, and managing cache entries within Redis, allowing for high-performance data retrieval and storage.

### Example Redis Caching Service

```c#
namespace CompanyTemplateProject.Core.Caching.RedisCacheService
{
    /// <summary>
    /// Service to interact with Redis cache.
    /// </summary>
    public class RedisCacheService : IRedisCacheService
    {
        private readonly IDatabase _redisDatabase;

        public RedisCacheService(IConnectionMultiplexer redisConnection)
        {
            _redisDatabase = redisConnection.GetDatabase();
        }

        /// <summary>
        /// Sets a value in the Redis cache with an expiration time.
        /// </summary>
        public async Task SetCacheValueAsync(string key, string value, TimeSpan expiration)
        {
            await _redisDatabase.StringSetAsync(key, value, expiration);
        }

        /// <summary>
        /// Gets a cached value from Redis by key.
        /// </summary>
        public async Task<string> GetCacheValueAsync(string key)
        {
            return await _redisDatabase.StringGetAsync(key);
        }
    }
}
```

In `appsettings.json`, you can configure the Redis connection and cache expiration policies to suit your deployment.

---

## Additional Resources

- [.NET Coding Conventions](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions)
- [Aspire Framework](https://github.com/dotnet/aspire)
- [AI Semantic Kernel Documentation](https://learn.microsoft.com/en-us/semantic-kernel)
- [Redis Documentation](https://redis.io/documentation)
- [Blazor WebAssembly Documentation](https://learn.microsoft.com/en-us/aspnet/core/blazor/?view=aspnetcore-7.0)

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.