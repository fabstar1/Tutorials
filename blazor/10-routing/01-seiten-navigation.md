# Seiten & Navigation

## Seite definieren

Jede Komponente mit `@page` Direktive ist eine eigene Seite.

```razor
@page "/produkte"

<h1>Produktliste</h1>
```

## Navigation mit NavLink

```razor
<nav>
    <NavLink href="/">Startseite</NavLink>
    <NavLink href="/produkte">Produkte</NavLink>
    <NavLink href="/kontakt">Kontakt</NavLink>
</nav>
```

`NavLink` fügt automatisch die CSS-Klasse `active` hinzu wenn die URL übereinstimmt.

## Programmatisch navigieren

```razor
@inject NavigationManager Nav

<button @onclick="ZurStartseite">Home</button>

@code {
    private void ZurStartseite() {
        Nav.NavigateTo("/");
    }
}
```

> **Das ist wichtig weil...** `NavLink` ist besser als `<a href>` in Blazor, weil es den aktiven Zustand automatisch verwaltet — nützlich für Navigationsmenüs.
