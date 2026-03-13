# Werte ausgeben

Mit `@` gibst du C#-Variablen und Ausdrücke direkt im HTML aus.

## Einfache Variablen

```razor
<p>Name: @name</p>
<p>Alter: @alter Jahre</p>
<p>Preis: @preis €</p>
<p>Aktiv: @istAktiv</p>

@code {
    private string name = "Anna";
    private int alter = 30;
    private double preis = 9.99;
    private bool istAktiv = true;
}
```

**Ausgabe:**
```
Name: Anna
Alter: 30 Jahre
Preis: 9.99 €
Aktiv: True
```

## Ausdrücke mit Klammern `@()`

Wenn der Ausdruck komplexer ist oder direkt neben Text steht, verwende `@()`:

```razor
<p>In 5 Jahren: @(alter + 5) Jahre alt</p>
<p>Preis mit MwSt: @(preis * 1.19) €</p>
<p>Status: @(istAktiv ? "Aktiv" : "Inaktiv")</p>
<p>@name hat den Buchstaben @(name.Length) Zeichen</p>
```

## Eigenschaften eines Objekts

```razor
<h2>@produkt.Name</h2>
<p>Preis: @produkt.Preis €</p>

@code {
    private Produkt produkt = new Produkt { Name = "Laptop", Preis = 999.99 };

    public class Produkt {
        public string Name { get; set; } = "";
        public double Preis { get; set; }
    }
}
```

## HTML-Attribute befüllen

```razor
<img src="@bildPfad" alt="Logo" />
<a href="@linkZiel">Zur Produktseite</a>
<button disabled="@istDeaktiviert">Klick</button>

@code {
    private string bildPfad = "images/logo.png";
    private string linkZiel = "/produkte";
    private bool istDeaktiviert = true;
}
```

> **Das ist wichtig weil...** Blazor aktualisiert die Anzeige automatisch, sobald sich eine Variable ändert. Du musst das HTML nie manuell anpassen.
