# Lifecycle

Blazor-Komponenten durchlaufen einen Lebenszyklus. Die wichtigste Methode für Anfänger ist `OnInitializedAsync`.

## Wichtigste Lifecycle-Methoden

```razor
@code {
    private List<Produkt> produkte = new();

    // Wird einmal aufgerufen wenn die Komponente geladen wird
    protected override async Task OnInitializedAsync() {
        produkte = await ProduktService.AlleAsync();
    }

    // Wird aufgerufen wenn sich Parameter ändern
    protected override void OnParametersSet() {
        // Reaktion auf neue Parameter
    }
}
```

| Methode | Wann |
|---------|------|
| `OnInitializedAsync` | Einmalig beim ersten Laden |
| `OnParametersSet` | Wenn Parameter sich ändern |
| `OnAfterRenderAsync` | Nach dem Rendern |

> **Das ist wichtig weil...** `OnInitializedAsync` ist die Standardmethode um Daten aus der Datenbank zu laden, wenn eine Seite aufgerufen wird.
