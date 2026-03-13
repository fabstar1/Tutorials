# Listen & LINQ

## Listen

```csharp
var namen = new List<string>();
namen.Add("Anna");
namen.Add("Ben");
namen.Remove("Ben");
int anzahl = namen.Count; // 1
```

## LINQ — Daten filtern und sortieren

```csharp
var produkte = new List<Produkt> {
    new Produkt { Name = "Laptop", Preis = 999 },
    new Produkt { Name = "Maus", Preis = 25 },
    new Produkt { Name = "Monitor", Preis = 350 }
};

// Filtern
var teuer = produkte.Where(p => p.Preis > 100).ToList();

// Sortieren
var sortiert = produkte.OrderBy(p => p.Preis).ToList();

// Erstes Element
var erstes = produkte.FirstOrDefault(p => p.Name == "Maus");
```

> **Das ist wichtig weil...** Dapper gibt Daten als `IEnumerable<T>` zurück. Mit LINQ filterst und sortierst du diese Daten direkt in C# — ohne extra SQL-Abfragen.
