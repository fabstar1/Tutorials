# C#-Blöcke & Direktiven

## @code — der Logik-Block

Alle C#-Felder, Methoden und Eigenschaften einer Komponente kommen in den `@code`-Block:

```razor
<p>Zähler: @zaehler</p>
<button @onclick="Erhöhen">+1</button>
<button @onclick="Zurücksetzen">Reset</button>

@code {
    private int zaehler = 0;

    private void Erhöhen() {
        zaehler++;
    }

    private void Zurücksetzen() {
        zaehler = 0;
    }
}
```

## @{ } — mehrzeiliger C#-Code im HTML

Für kurze C#-Logik direkt im Template (selten nötig):

```razor
@{
    var begrüßung = DateTime.Now.Hour < 12 ? "Guten Morgen" : "Guten Tag";
    var cssKlasse = zaehler > 10 ? "text-danger" : "text-success";
}

<p class="@cssKlasse">@begrüßung! Zähler: @zaehler</p>
```

## Wichtige Direktiven

Direktiven stehen ganz oben in der `.razor`-Datei:

```razor
@page "/meine-seite"           <!-- URL dieser Seite -->
@using MeinProjekt.Models      <!-- Namespace einbinden -->
@inject IProduktService Svc    <!-- Service injizieren -->
```

| Direktive | Bedeutung |
|-----------|-----------|
| `@page "/pfad"` | Macht die Komponente zu einer Seite mit URL |
| `@using Namespace` | Bindet einen Namespace ein (wie `using` in C#) |
| `@inject Typ Name` | Holt einen Service per Dependency Injection |
| `@code { }` | C#-Logik-Block der Komponente |

## Kommentare

```razor
@* Das ist ein Razor-Kommentar — wird nicht im HTML ausgegeben *@

<!-- Das ist ein HTML-Kommentar — wird im Browser-Quelltext sichtbar -->
```

> **Das ist wichtig weil...** `@page` und `@inject` sind in fast jeder Blazor-Seite vorhanden. Ohne sie funktionieren weder Navigation noch Services.
