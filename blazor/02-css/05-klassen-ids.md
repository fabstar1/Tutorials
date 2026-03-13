# Klassen & IDs

## Klassen

Klassen können mehrfach verwendet werden. Sie sind das Standard-Werkzeug in Blazor.

```html
<div class="karte">Inhalt A</div>
<div class="karte hervorgehoben">Inhalt B</div>
```

```css
.karte {
    border: 1px solid #ccc;
    padding: 12px;
}

.hervorgehoben {
    border-color: blue;
}
```

## IDs

IDs sind einmalig auf einer Seite.

```html
<div id="haupt-inhalt">...</div>
```

```css
#haupt-inhalt {
    max-width: 1200px;
    margin: 0 auto;
}
```

## In Blazor: dynamische Klassen

```razor
<div class="@(IstAktiv ? "aktiv" : "")">Inhalt</div>
```

> **Das ist wichtig weil...** In Blazor fügst du Klassen oft dynamisch je nach Zustand hinzu (aktiv, deaktiviert, fehler). Das geht mit dem `@`-Ausdruck direkt im HTML.
