# Dapper Setup & Konfiguration

## NuGet-Pakete installieren

```bash
dotnet add package Dapper
dotnet add package Microsoft.Data.SqlClient
```

## Connection String in appsettings.json

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=localhost;Database=MeineDb;User Id=sa;Password=geheim;TrustServerCertificate=True"
  }
}
```

## Datenbankverbindung registrieren (Program.cs)

```csharp
using System.Data;               // für IDbConnection und CommandType
using Microsoft.Data.SqlClient;

// Program.cs
builder.Services.AddScoped<IDbConnection>(sp =>
    new SqlConnection(
        builder.Configuration.GetConnectionString("DefaultConnection")
    )
);
```

## Im Service nutzen

```csharp
public class ProduktService {
    private readonly IDbConnection _db;

    public ProduktService(IDbConnection db) {
        _db = db;
    }
}
```

> **Das ist wichtig weil...** Die Datenbankverbindung wird einmal in `Program.cs` konfiguriert und dann per Dependency Injection in jeden Service injiziert. Der Connection String steht in `appsettings.json` — nie im Code hardcoden!
