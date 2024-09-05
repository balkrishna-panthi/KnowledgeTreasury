# What are builders in .Net core and what are they used for ?

# Comprehensive Guide to Builders in .NET Core

## Introduction

Builders in .NET Core facilitate the configuration and setup of various application components in a modular and fluent manner. They help streamline the setup process for hosts, web servers, configurations, and dependency injection.

## 1. HostBuilder

### Overview

The `HostBuilder` is used for creating and configuring a host for .NET Core applications, including console apps, worker services, and more. It handles application services, configuration sources, and logging.

### Key Features

- **Application Services**: Configure and add services required by the application.
- **Configuration**: Integrate configuration sources like JSON files and environment variables.
- **Logging**: Configure logging services and providers.

### Usage

**Basic Setup:**

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureAppConfiguration((context, config) =>
        {
            config.AddJsonFile("appsettings.json", optional: false, reloadOnChange: true)
                  .AddEnvironmentVariables();
        })
        .ConfigureServices((context, services) =>
        {
            services.AddControllersWithViews();
            // Register additional services
        })
        .ConfigureLogging(logging =>
        {
            logging.ClearProviders();
            logging.AddConsole();
        });
