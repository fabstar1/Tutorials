# Dependency Injection

Dependency Injection (DI) stellt Services automatisch bereit, ohne dass du sie selbst erstellen musst.

## Service registrieren (Program.cs)

```csharp
// Program.cs
builder.Services.AddScoped<IProduktService, ProduktService>();
builder.Services.AddScoped<IBenutzerService, BenutzerService>();
```

## Service in Komponente nutzen

```razor
@inject IProduktService ProduktService

<ul>
    @foreach (var p in produkte) {
        <li>@p.Name</li>
    }
</ul>

@code {
    private List<Produkt> produkte = new();

    protected override async Task OnInitializedAsync() {
        produkte = await ProduktService.AlleAsync();
    }
}
```

## Lebensdauer (Lifetime)

| Typ | Bedeutung |
|-----|-----------|
| `AddScoped` | Einmal pro Benutzer-Session (Standard für Blazor Server) |
| `AddSingleton` | Einmal für die gesamte App |
| `AddTransient` | Jedes Mal neu |

> **Das ist wichtig weil...** `AddScoped` ist der richtige Standard für Blazor Server. Jeder Benutzer bekommt seine eigene Service-Instanz.
