# One-Way Binding

Daten fließen nur in eine Richtung: von C# → HTML.

## Beispiel

```razor
<h2>@titel</h2>
<p>Preis: @preis €</p>
<p>Aktiv: @(istAktiv ? "Ja" : "Nein")</p>

@code {
    private string titel = "Mein Produkt";
    private double preis = 9.99;
    private bool istAktiv = true;
}
```

## Attribute binden

```razor
<img src="@bildUrl" alt="Produktbild" />
<button disabled="@istDeaktiviert">Klick</button>
```

> **Das ist wichtig weil...** One-Way Binding ist der einfachste Fall — du zeigst Daten an. Für Eingabefelder brauchst du Two-Way Binding.
