# Bootstrap

Bootstrap ist ein kostenloses CSS-Framework von Twitter. Es liefert fertige Klassen für Layouts, Buttons, Formulare, Tabellen und vieles mehr — ohne dass du CSS von Grund auf schreiben musst.

## Warum Bootstrap?

Ohne Bootstrap musst du für jeden Button, jede Tabelle und jedes Layout eigenes CSS schreiben:

```html
<!-- Ohne Bootstrap: alles von Hand stylen -->
<button style="background-color: #0d6efd; color: white; padding: 8px 16px;
               border: none; border-radius: 4px; font-size: 16px; cursor: pointer;">
    Speichern
</button>

<table style="width: 100%; border-collapse: collapse; font-family: Arial, sans-serif;">
    <thead style="background-color: #f8f9fa;">
        <tr>
            <th style="padding: 12px; border: 1px solid #dee2e6; text-align: left;">Name</th>
            <th style="padding: 12px; border: 1px solid #dee2e6; text-align: left;">Preis</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="padding: 12px; border: 1px solid #dee2e6;">Laptop</td>
            <td style="padding: 12px; border: 1px solid #dee2e6;">999 €</td>
        </tr>
    </tbody>
</table>
```

Mit Bootstrap ersetzt du all das durch kurze, lesbare Klassen:

```html
<!-- Mit Bootstrap: fertige Klassen nutzen -->
<button class="btn btn-primary">Speichern</button>

<table class="table table-bordered">
    <thead class="table-light">
        <tr>
            <th>Name</th>
            <th>Preis</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Laptop</td>
            <td>999 €</td>
        </tr>
    </tbody>
</table>
```

Das Ergebnis sieht professionell aus — ohne eine einzige Zeile eigenes CSS.

## Bootstrap in Blazor einbinden

In `wwwroot/index.html` oder `App.razor` (je nach .NET-Version):

```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet" />
```

Oder per NuGet:

```bash
dotnet add package Bootstrap
```

## Themen

- [Layout & Grid](./01-grid.md)
- [Buttons & Farben](./02-buttons-farben.md)
- [Tabellen](./03-tabellen.md)
- [Formulare](./04-formulare.md)
- [Abstände & Hilfklassen](./05-abstaende.md)

> **Das ist wichtig weil...** Bootstrap spart enorm viel Zeit. Statt stundenlang CSS zu schreiben, nutzt du fertige, getestete Klassen. Fast alle professionellen Blazor-Apps verwenden Bootstrap oder ein ähnliches Framework.
