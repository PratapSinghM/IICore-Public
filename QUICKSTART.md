# Quick Start Guide

Get up and running with IICore in 5 minutes!

## Prerequisites

Ensure you have:
- **.NET 6.0 SDK** (download from [dotnet.microsoft.com](https://dotnet.microsoft.com))
- **MariaDB/MySQL** (or any compatible database)
- **Git** for cloning the repository

## 📥 Installation Steps

### 1. Clone the Repository
```bash
git clone https://github.com/PratapSinghM/IICore-Public.git
cd IICore-Public
```

### 2. Create Configuration File
Create `IICore.API/appsettings.Development.json`:

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    }
  },
  "AllowedHosts": "*",
  "RedisURL": "127.0.0.1:6379",
  "JWT": {
    "ValidAudience": "http://localhost:5006",
    "ValidIssuer": "http://localhost:5006",
    "Secret": "YOUR_RANDOM_JWT_SECRET_KEY_HERE"
  },
  "ConnectionStrings": {
    "DefaultConnection": "Server=localhost; Port=3306; Database=iicoreapi_dev; Uid=root; Pwd=YOUR_PASSWORD;"
  }
}
```

### 3. Set Up Database
```bash
# Create database
mysql -u root -p -e "CREATE DATABASE iicoreapi_dev;"

# Run migrations
cd IICore.API
dotnet ef database update
cd ..
```

### 4. Restore & Run
```bash
# Restore NuGet packages
dotnet restore

# Run the application
dotnet run --project IICore.API/IICore.API.csproj
```

### 5. Access the API
Open your browser and navigate to:
- **Swagger UI**: http://localhost:5006/swagger
- **Health Check**: http://localhost:5006/health

## 🚀 What's Next?

- Read [SETUP.md](../SETUP.md) for detailed configuration
- Check [CONTRIBUTING.md](../CONTRIBUTING.md) for contribution guidelines
- Review [README.md](../README.md) for full project documentation

## 🆘 Troubleshooting

### Database Connection Failed
```
Error: Connection refused at 127.0.0.1:3306
```
**Solution**: Ensure MariaDB/MySQL is running and credentials in `appsettings.Development.json` are correct.

### Port Already in Use
```
Error: Address already in use
```
**Solution**: Change the port in `launchSettings.json` or kill the process using port 5006.

### Build Fails
```
Error: Unable to restore packages
```
**Solution**: Clear NuGet cache and restore again:
```bash
dotnet nuget locals all --clear
dotnet restore
```

### JWT Secret Issues
```
Error: Invalid token
```
**Solution**: Ensure `JWT.Secret` in configuration is set to a strong random value (minimum 32 characters).

## 📚 Common Commands

```bash
# Run tests
dotnet test

# Build release
dotnet build --configuration Release

# Clean build artifacts
dotnet clean

# Update packages
dotnet package update

# Create migration
dotnet ef migrations add YourMigrationName --project IICore.API

# View database
mysql -u root -p iicoreapi_dev
```

## 🔐 Security Reminder

⚠️ **Never commit**:
- `appsettings.Development.json` with real credentials
- `.env` files with secrets
- API keys or passwords

These are git-ignored automatically.

## 📖 Additional Resources

| Resource | Link |
|----------|------|
| .NET Documentation | https://docs.microsoft.com/dotnet |
| Entity Framework | https://docs.microsoft.com/ef/core |
| ASP.NET Core | https://docs.microsoft.com/aspnet/core |
| MySQL Documentation | https://dev.mysql.com/doc |

## 💬 Need Help?

- Check [Discussions](https://github.com/PratapSinghM/IICore-Public/discussions)
- Review [Issues](https://github.com/PratapSinghM/IICore-Public/issues)
- Read [SETUP.md](../SETUP.md) for advanced configuration

---

**You're all set!** Happy coding! 🎉
