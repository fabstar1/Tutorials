# Variablen & Typen

In C# muss jede Variable einen Typ haben. Der Compiler weiß damit, welche Operationen erlaubt sind.

## Beispiel

```csharp
// Zahlen
int alter = 30;
double preis = 9.99;

// Text
string name = "Anna";

// Wahrheitswert
bool istAktiv = true;

// Typ automatisch erkennen (empfohlen)
var nachricht = "Hallo Welt";
var zahl = 42;
```

| Typ | Beispiel | Verwendung |
|-----|---------|------------|
| `int` | `42` | Ganze Zahlen |
| `double` | `3.14` | Kommazahlen |
| `string` | `"Text"` | Zeichenketten |
| `bool` | `true` / `false` | Ja/Nein |
| `var` | automatisch | Typ wird erkannt |

> **Das ist wichtig weil...** In Blazor-Komponenten deklarierst du Felder und Properties genau so. `var` ist in der Praxis am häufigsten.
