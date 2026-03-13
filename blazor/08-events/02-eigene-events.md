# Eigene Events (EventCallback)

Mit `EventCallback` kann eine Kindkomponente Ereignisse an die Elternkomponente melden.

## Beispiel

```razor
@* Datei: Components/LöschButton.razor *@

<button @onclick="HandleKlick">Löschen</button>

@code {
    [Parameter]
    public EventCallback<int> OnLöschen { get; set; }

    [Parameter]
    public int ItemId { get; set; }

    private async Task HandleKlick() {
        await OnLöschen.InvokeAsync(ItemId);
    }
}
```

```razor
@* Verwendung in Elternkomponente *@
<LöschButton ItemId="3" OnLöschen="ItemGelöscht" />

@code {
    private void ItemGelöscht(int id) {
        Console.WriteLine($"Item {id} wurde gelöscht");
    }
}
```

> **Das ist wichtig weil...** Daten fließen in Blazor nach unten (Parameter), Events nach oben (EventCallback). Das ist das Grundprinzip der Komponentenkommunikation.
