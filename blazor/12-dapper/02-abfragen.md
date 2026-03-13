# Daten abfragen (SELECT)

Bei Stored Procedures wird immer `commandType: CommandType.StoredProcedure` angegeben. Dafür muss `System.Data` eingebunden sein.

## Alle Datensätze laden

```csharp
public async Task<List<Produkt>> AlleAsync() {
    return (await _db.QueryAsync<Produkt>(
        "sp_Produkte_GetAll",
        commandType: CommandType.StoredProcedure
    )).ToList();
}
```

## Einen Datensatz per ID laden

```csharp
public async Task<Produkt?> FindeAsync(int id) {
    return await _db.QueryFirstOrDefaultAsync<Produkt>(
        "sp_Produkte_GetById",
        new { Id = id },
        commandType: CommandType.StoredProcedure
    );
}
```

## Mit mehreren Parametern

```csharp
public async Task<List<Produkt>> SucheAsync(string suchbegriff, double maxPreis) {
    return (await _db.QueryAsync<Produkt>(
        "sp_Produkte_Suche",
        new { Suchbegriff = suchbegriff, MaxPreis = maxPreis },
        commandType: CommandType.StoredProcedure
    )).ToList();
}
```

| Methode | Rückgabe |
|---------|---------|
| `QueryAsync<T>` | Liste aller Treffer |
| `QueryFirstOrDefaultAsync<T>` | Erstes Ergebnis oder `null` |
| `QuerySingleAsync<T>` | Genau ein Ergebnis (Fehler wenn keins) |

> **Das ist wichtig weil...** Die Parameter werden als anonymes Objekt übergeben — die Namen müssen exakt mit den Parameternamen der Stored Procedure in der Datenbank übereinstimmen (z.B. `@Suchbegriff`).
