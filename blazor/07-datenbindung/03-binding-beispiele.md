# Binding Beispiele

Praktische Beispiele für häufige Bindungsszenarien.

## Dropdown

```razor
<select @bind="ausgewähltesLand">
    <option value="">-- Bitte wählen --</option>
    <option value="de">Deutschland</option>
    <option value="at">Österreich</option>
</select>
<p>Gewählt: @ausgewähltesLand</p>

@code {
    private string ausgewähltesLand = "";
}
```

## Liste anzeigen

```razor
@foreach (var item in produkte) {
    <div>@item.Name — @item.Preis €</div>
}

@code {
    private List<Produkt> produkte = new() {
        new Produkt { Name = "Laptop", Preis = 999 },
        new Produkt { Name = "Maus", Preis = 25 }
    };
}
```

> **Das ist wichtig weil...** Diese Muster — Liste rendern, Dropdown binden — kommen in fast jeder Blazor-Anwendung vor.
