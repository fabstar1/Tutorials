# Tabellen

Bootstrap macht Tabellen mit wenigen Klassen sofort ansehnlich.

## Beispiel

```html
<table class="table">
    <thead>
        <tr>
            <th>Name</th>
            <th>Preis</th>
            <th>Aktionen</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Laptop</td>
            <td>999 €</td>
            <td><button class="btn btn-sm btn-danger">Löschen</button></td>
        </tr>
    </tbody>
</table>
```

## Varianten

```html
<!-- Mit Rahmen -->
<table class="table table-bordered">

<!-- Jede zweite Zeile grau -->
<table class="table table-striped">

<!-- Zeile beim Hover hervorheben -->
<table class="table table-hover">

<!-- Kombiniert -->
<table class="table table-bordered table-striped table-hover">

<!-- Kompakter -->
<table class="table table-sm">
```

## In Blazor mit @foreach

```razor
<table class="table table-striped table-hover">
    <thead>
        <tr>
            <th>Name</th>
            <th>Preis</th>
        </tr>
    </thead>
    <tbody>
        @foreach (var produkt in produkte) {
            <tr>
                <td>@produkt.Name</td>
                <td>@produkt.Preis €</td>
            </tr>
        }
    </tbody>
</table>
```

> **Das ist wichtig weil...** Datentabellen sind in Business-Anwendungen allgegenwärtig. `table-striped` und `table-hover` verbessern die Lesbarkeit sofort ohne eigenes CSS.
