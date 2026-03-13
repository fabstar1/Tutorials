# Layout & Grid

Das Bootstrap Grid-System teilt eine Seite in 12 Spalten auf. Du bestimmst, wie viele Spalten ein Element einnehmen soll.

## Grundprinzip

```html
<div class="container">
    <div class="row">
        <div class="col-6">Linke Hälfte</div>
        <div class="col-6">Rechte Hälfte</div>
    </div>
</div>
```

## Responsive Spalten

```html
<div class="container">
    <div class="row">
        <!-- Auf Handy: volle Breite, ab Tablet: halbe Breite -->
        <div class="col-12 col-md-6">
            <p>Inhalt links</p>
        </div>
        <div class="col-12 col-md-6">
            <p>Inhalt rechts</p>
        </div>
    </div>
</div>
```

## Drei gleichmäßige Spalten

```html
<div class="container">
    <div class="row">
        <div class="col-4">Spalte 1</div>
        <div class="col-4">Spalte 2</div>
        <div class="col-4">Spalte 3</div>
    </div>
</div>
```

| Klasse | Breite |
|--------|--------|
| `col-12` | 100% (volle Zeile) |
| `col-6` | 50% (halbe Zeile) |
| `col-4` | 33% (ein Drittel) |
| `col-3` | 25% (ein Viertel) |

> **Das ist wichtig weil...** Das Grid-System macht deine App auf allen Bildschirmgrößen nutzbar — Handy, Tablet und Desktop. `container` zentriert den Inhalt und gibt ihm eine maximale Breite.
