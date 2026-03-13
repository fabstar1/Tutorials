# Parameter

Mit Parametern übergibst du Daten von einer übergeordneten an eine untergeordnete Komponente.

## Beispiel

```razor
@* Datei: Components/Begrüßung.razor *@

<p>Hallo, @Name! Du bist @Alter Jahre alt.</p>

@code {
    [Parameter]
    public string Name { get; set; } = "";

    [Parameter]
    public int Alter { get; set; }
}
```

```razor
@* Verwendung in einer anderen Komponente: *@
<Begrüßung Name="Anna" Alter="30" />
```

> **Das ist wichtig weil...** Parameter machen Komponenten wiederverwendbar. Statt eine Komponente für jeden Benutzer zu bauen, baust du eine und gibst den Namen als Parameter mit.
