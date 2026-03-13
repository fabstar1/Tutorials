# Klassen & Objekte

Klassen sind Baupläne. Objekte sind konkrete Instanzen davon.

## Beispiel

```csharp
// Klasse definieren
public class Produkt {
    public int Id { get; set; }
    public string Name { get; set; } = "";
    public double Preis { get; set; }
}

// Objekt erstellen
var produkt = new Produkt {
    Id = 1,
    Name = "Laptop",
    Preis = 999.99
};

Console.WriteLine(produkt.Name); // "Laptop"
```

## Record (einfache Alternative)

```csharp
public record Produkt(int Id, string Name, double Preis);

var p = new Produkt(1, "Laptop", 999.99);
```

> **Das ist wichtig weil...** In Blazor modellierst du Daten als Klassen — z.B. `Benutzer`, `Bestellung`, `Produkt`. Diese Klassen übergibst du dann an Komponenten als Parameter.
