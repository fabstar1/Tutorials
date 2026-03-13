# Bedingungen & Schleifen

Mit `@if` und `@foreach` steuerst du, was angezeigt wird — direkt im HTML.

## @if — Bedingtes Anzeigen

```razor
@if (istAngemeldet) {
    <p>Willkommen zurück!</p>
} else {
    <p>Bitte melde dich an.</p>
}

@if (anzahlArtikel == 0) {
    <p class="text-muted">Keine Artikel vorhanden.</p>
} else if (anzahlArtikel == 1) {
    <p>1 Artikel im Warenkorb.</p>
} else {
    <p>@anzahlArtikel Artikel im Warenkorb.</p>
}

@code {
    private bool istAngemeldet = true;
    private int anzahlArtikel = 0;
}
```

## @foreach — Liste anzeigen

```razor
<ul>
    @foreach (var name in namen) {
        <li>@name</li>
    }
</ul>

@code {
    private List<string> namen = new() { "Anna", "Ben", "Clara" };
}
```

## @foreach mit Objekten

```razor
<table class="table">
    <thead>
        <tr><th>Name</th><th>Preis</th></tr>
    </thead>
    <tbody>
        @foreach (var p in produkte) {
            <tr>
                <td>@p.Name</td>
                <td>@p.Preis €</td>
            </tr>
        }
    </tbody>
</table>

@code {
    private List<Produkt> produkte = new() {
        new Produkt { Name = "Laptop", Preis = 999 },
        new Produkt { Name = "Maus", Preis = 25 },
        new Produkt { Name = "Monitor", Preis = 350 }
    };

    public class Produkt {
        public string Name { get; set; } = "";
        public double Preis { get; set; }
    }
}
```

## @for — Schleife mit Index

```razor
@for (int i = 1; i <= 5; i++) {
    <p>Zeile @i</p>
}
```

> **Das ist wichtig weil...** `@foreach` ist eines der meistgenutzten Razor-Konstrukte. Jede Liste, jede Tabelle in Blazor wird damit gerendert.
