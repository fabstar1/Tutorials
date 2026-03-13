# Methoden

Methoden fassen wiederverwendbare Logik zusammen.

## Beispiel

```csharp
// Methode ohne Rückgabewert
void BegrüßeBenutzer(string name) {
    Console.WriteLine($"Hallo, {name}!");
}

// Methode mit Rückgabewert
int Addiere(int a, int b) {
    return a + b;
}

// Aufruf
BegrüßeBenutzer("Anna");
int ergebnis = Addiere(3, 4); // ergebnis = 7
```

## Async-Methoden (für Blazor wichtig)

```csharp
async Task LadeDatenAsync() {
    var daten = await datenbankService.AlleEinträgeAsync();
    // Daten verarbeiten...
}
```

> **Das ist wichtig weil...** In Blazor-Komponenten schreibst du viele Methoden im `@code { }` Block — z.B. für Button-Klicks oder das Laden von Daten beim Start. Async ist dabei Standard.
