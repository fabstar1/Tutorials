# Parameter in URLs

URL-Parameter erlauben es, Daten über die URL zu übergeben.

## Beispiel

```razor
@page "/produkt/{Id:int}"

<h1>Produkt: @produkt?.Name</h1>

@code {
    [Parameter]
    public int Id { get; set; }

    private Produkt? produkt;

    protected override async Task OnParametersSetAsync() {
        produkt = await ProduktService.FindeAsync(Id);
    }
}
```

## Aufruf

```razor
<NavLink href="/produkt/42">Produkt 42 anzeigen</NavLink>

@* Oder programmatisch: *@
Nav.NavigateTo($"/produkt/{produkt.Id}");
```

## Typen in URL-Parametern

| Typ | Beispiel |
|-----|---------|
| `{Id:int}` | `/produkt/42` |
| `{Name}` | `/produkt/laptop` |
| `{Id:guid}` | `/item/abc-123-...` |

> **Das ist wichtig weil...** Detail-Seiten (Produkt, Benutzer, Bestellung) brauchen immer eine ID in der URL. Das ist das Standardmuster in Blazor-Anwendungen.
