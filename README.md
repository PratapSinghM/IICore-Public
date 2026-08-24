# IICore - Image Identification and Recognition System

A comprehensive .NET 6.0 application for image identification, processing, and text classification using modern cloud architecture.

## 🎯 Features

- **Image Processing** - Advanced image reading and manipulation
- **Image Identification** - AI-powered image recognition
- **Text Classification** - NLP-based text analysis
- **Data Extraction** - Extract structured data from images
- **REST API** - Full-featured HTTP API with JWT authentication
- **Redis Caching** - Performance optimization with Redis
- **Azure Integration** - Cloud-ready with Azure SQL/Functions support

## 🛠️ Tech Stack

- **.NET 6.0** - Modern C# framework
- **Entity Framework Core** - ORM with migrations
- **ASP.NET Core** - REST API framework
- **MariaDB/MySQL** - Primary database
- **Redis** - Caching layer
- **Azure** - Cloud infrastructure

## 📋 Prerequisites

- .NET 6.0 SDK or later
- MariaDB/MySQL 5.7+
- Redis 6.0+ (optional)
- Visual Studio 2022 or VS Code

## 🚀 Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/PratapSinghM/IICore-Public.git
   cd IICore-Public
   ```

2. **Configure your environment**
   - Follow [SETUP.md](./SETUP.md) for detailed configuration steps

3. **Install dependencies**
   ```bash
   dotnet restore
   ```

4. **Run migrations**
   ```bash
   cd IICore.API
   dotnet ef database update
   ```

5. **Start the application**
   ```bash
   dotnet run
   ```

The API will be available at `http://localhost:5006`

## 📚 Project Structure

| Module | Purpose |
|--------|---------|
| `IICore.API` | Main REST API and application entry point |
| `IICore.Common` | Shared utilities and helpers |
| `IICore.ImageReader` | Image file reading and basic processing |
| `IICore.ImageIdentifier` | AI-powered image identification |
| `IICore.TextClassification` | Text classification and NLP |
| `IICore.DataExtraction` | Extract data from images |
| `IICore.ImageConversion` | Format conversion and optimization |

## 🔐 Security

This repository does **NOT** contain sensitive data:
- ✅ Configuration files use placeholder values
- ✅ Database credentials are excluded
- ✅ API keys are not committed
- ✅ Secrets are managed via environment variables

**For local development**, see [SETUP.md](./SETUP.md) to configure your own credentials.

## 🔄 API Authentication

The API uses **JWT (JSON Web Tokens)** for authentication:

```bash
# Example: Get JWT token
POST /api/auth/login
Content-Type: application/json

{
  "username": "user@example.com",
  "password": "password"
}
```

Use the returned token in the `Authorization` header:
```
Authorization: Bearer YOUR_JWT_TOKEN
```

## 📖 API Documentation

- **Swagger UI**: Available at `/swagger` when running locally
- **API Endpoints**: See individual module documentation
- **Authentication**: JWT tokens required for most endpoints

## 🧪 Testing

```bash
# Run unit tests
dotnet test

# Run with coverage
dotnet test /p:CollectCoverage=true
```

## 📝 Database Migrations

```bash
# Create a new migration
dotnet ef migrations add YourMigrationName --project IICore.API

# Apply migrations
dotnet ef database update --project IICore.API

# Revert last migration
dotnet ef database update PreviousMigrationName --project IICore.API
```

## 🤝 Contributing

We welcome contributions! Please:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** changes (`git commit -m "Add amazing feature"`)
4. **Push** to branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

### Before Submitting a PR:
- Ensure no secrets are committed
- Follow C# coding standards
- Add tests for new features
- Update documentation

## ⚠️ Before Going Public

**IMPORTANT**: If you're planning to make this repository public:
- [ ] Review all configuration files for secrets
- [ ] Ensure `.gitignore` is properly configured
- [ ] Rotate all development/staging credentials
- [ ] Update documentation with proper setup instructions
- [ ] Remove any internal/proprietary information

## 📄 License

[Specify your license - e.g., MIT, Apache 2.0, etc.]

## 📞 Support & Issues

- **Found a bug?** [Open an Issue](https://github.com/PratapSinghM/IICore-Public/issues)
- **Feature request?** [Create a Discussion](https://github.com/PratapSinghM/IICore-Public/discussions)
- **Security issue?** Please email directly instead of opening a public issue

## 📚 Additional Resources

- [.NET Documentation](https://docs.microsoft.com/dotnet)
- [Entity Framework Core](https://docs.microsoft.com/ef/core)
- [ASP.NET Core API](https://docs.microsoft.com/aspnet/core)
- [JWT Authentication](https://jwt.io)

---

**Happy coding!** 🎉
