# Eigene Services erstellen

## Interface definieren

```csharp
// Services/IProduktService.cs
public interface IProduktService {
    Task<List<Produkt>> AlleAsync();
    Task<Produkt?> FindeAsync(int id);
    Task SpeichernAsync(Produkt produkt);
    Task LöschenAsync(int id);
}
```

## Service implementieren

```csharp
// Services/ProduktService.cs
public class ProduktService : IProduktService {
    private readonly IDbConnection _db;

    public ProduktService(IDbConnection db) {
        _db = db;
    }

    public async Task<List<Produkt>> AlleAsync() {
        var sql = "SELECT * FROM Produkte";
        var ergebnis = await _db.QueryAsync<Produkt>(sql);
        return ergebnis.ToList();
    }

    // weitere Methoden implementieren...
}
```

## Registrieren

```csharp
// Program.cs
builder.Services.AddScoped<IProduktService, ProduktService>();
```

> **Das ist wichtig weil...** Das Interface ermöglicht es, den Service später auszutauschen (z.B. für Tests). Das ist gutes Software-Design.
