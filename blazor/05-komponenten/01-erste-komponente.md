# Erste Komponente

Eine Blazor-Komponente ist eine `.razor`-Datei mit drei optionalen Bereichen.

## Aufbau

```razor
@* Datei: Components/MeinKomponent.razor *@

<!-- 1. HTML-Teil -->
<h2>Hallo, @name!</h2>
<button @onclick="NameÄndern">Klick mich</button>

@code {
    // 2. C#-Logik
    private string name = "Welt";

    private void NameÄndern() {
        name = "Blazor";
    }
}
```

## Komponente verwenden

```razor
@* In einer anderen Komponente: *@
<MeinKomponent />
```

> **Das ist wichtig weil...** Das `@`-Zeichen verbindet HTML und C# in Blazor. `@name` gibt den Wert der Variable aus. `@onclick` reagiert auf Klicks.
