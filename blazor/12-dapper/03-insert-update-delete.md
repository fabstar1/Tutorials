# Daten ändern (INSERT, UPDATE, DELETE)

Für datenverändernde Stored Procedures wird `ExecuteAsync` verwendet.

## INSERT

```csharp
public async Task ErstellenAsync(Produkt produkt) {
    await _db.ExecuteAsync(
        "sp_Produkte_Insert",
        new { produkt.Name, produkt.Preis },
        commandType: CommandType.StoredProcedure
    );
}
```

## INSERT mit neuer ID

```csharp
public async Task<int> ErstellenMitIdAsync(Produkt produkt) {
    return await _db.QuerySingleAsync<int>(
        "sp_Produkte_Insert",
        new { produkt.Name, produkt.Preis },
        commandType: CommandType.StoredProcedure
    );
}
```

Die Stored Procedure gibt die neue ID zurück:
```sql
CREATE PROCEDURE sp_Produkte_Insert
    @Name NVARCHAR(100),
    @Preis FLOAT
AS
BEGIN
    INSERT INTO Produkte (Name, Preis) VALUES (@Name, @Preis);
    SELECT CAST(SCOPE_IDENTITY() AS INT);
END
```

## UPDATE

```csharp
public async Task AktualisierenAsync(Produkt produkt) {
    await _db.ExecuteAsync(
        "sp_Produkte_Update",
        new { produkt.Id, produkt.Name, produkt.Preis },
        commandType: CommandType.StoredProcedure
    );
}
```

## DELETE

```csharp
public async Task LöschenAsync(int id) {
    await _db.ExecuteAsync(
        "sp_Produkte_Delete",
        new { Id = id },
        commandType: CommandType.StoredProcedure
    );
}
```

> **Das ist wichtig weil...** Durch Stored Procedures liegt die gesamte SQL-Logik in der Datenbank — der C#-Code bleibt schlank und muss nicht angepasst werden, wenn sich das SQL ändert.
