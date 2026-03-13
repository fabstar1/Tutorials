# Datenbankzugriff mit Dapper

Dapper ist ein schlanker SQL-Mapper für .NET. Er übersetzt Datenbankabfragen direkt in C#-Objekte — ohne großes Framework drumherum.

## Warum Dapper?

- **Einfach** — im Wesentlichen drei Methoden: `QueryAsync`, `QueryFirstOrDefaultAsync`, `ExecuteAsync`
- **Transparent** — kein automatisch erzeugtes SQL, kein verstecktes Verhalten
- **Schnell** — minimaler Overhead, einer der schnellsten .NET-Datenzugriffe überhaupt
- **Flexibel** — funktioniert mit jeder bestehenden Datenbankstruktur

Im Vergleich zu Entity Framework erzeugst du kein SQL im Dunkeln — du weißt immer genau, was ausgeführt wird.

## Stored Procedures vs. direktes SQL

In diesem Projekt nutzen wir **Stored Procedures**. Dapper unterstützt aber auch direktes SQL — praktisch für schnelle Abfragen oder Debugging:

```csharp
// Direktes SQL (z.B. zum Testen)
var produkte = await _db.QueryAsync<Produkt>("SELECT * FROM Produkte WHERE Preis < @Max", new { Max = 100 });

// Stored Procedure (Standard in diesem Projekt)
var produkte = await _db.QueryAsync<Produkt>("sp_Produkte_GetAll", commandType: CommandType.StoredProcedure);
```

## Themen

- [Setup & Konfiguration](./01-setup.md)
- [Abfragen (SELECT)](./02-abfragen.md)
- [Daten ändern (INSERT, UPDATE, DELETE)](./03-insert-update-delete.md)

> **Das ist wichtig weil...** Dapper hält den Datenbankzugriff einfach und nachvollziehbar — ideal für Einsteiger und schnelle Entwicklung.
