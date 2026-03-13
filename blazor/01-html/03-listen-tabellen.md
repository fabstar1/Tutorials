# Listen & Tabellen

Listen und Tabellen helfen dir, Daten strukturiert darzustellen.

## Listen

```html
<!-- Ungeordnete Liste (Punkte) -->
<ul>
    <li>Apfel</li>
    <li>Banane</li>
</ul>

<!-- Geordnete Liste (Nummern) -->
<ol>
    <li>Erster Schritt</li>
    <li>Zweiter Schritt</li>
</ol>
```

## Tabellen

```html
<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Alter</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Anna</td>
            <td>30</td>
        </tr>
    </tbody>
</table>
```

> **Das ist wichtig weil...** In Blazor wirst du oft Listen mit `@foreach` rendern — das erzeugt immer `<li>` oder `<tr>` Elemente. Das Grundprinzip ist dasselbe.
