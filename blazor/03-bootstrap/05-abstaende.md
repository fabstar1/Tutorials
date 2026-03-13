# Abstände & Hilfsklassen

Bootstrap hat Kurzklassen für die häufigsten CSS-Eigenschaften — das spart viel eigenes CSS.

## Abstände (Spacing)

Das Schema ist: `{eigenschaft}{seite}-{größe}`

```html
<!-- margin (Außenabstand) -->
<div class="m-3">Rundum Abstand</div>
<div class="mt-3">Oben (top)</div>
<div class="mb-3">Unten (bottom)</div>
<div class="ms-3">Links (start)</div>
<div class="me-3">Rechts (end)</div>
<div class="mx-3">Links + Rechts</div>
<div class="my-3">Oben + Unten</div>

<!-- padding (Innenabstand) -->
<div class="p-3">Innenabstand rundum</div>
<div class="px-4 py-2">Horizontal 4, Vertikal 2</div>
```

Größen: `0` = 0px, `1` = 4px, `2` = 8px, `3` = 16px, `4` = 24px, `5` = 48px

## Text

```html
<p class="text-center">Zentriert</p>
<p class="text-end">Rechtsbündig</p>
<p class="fw-bold">Fett</p>
<p class="text-muted">Grau/gedimmt</p>
<p class="text-danger">Rot (für Fehler)</p>
<p class="text-success">Grün (für Erfolg)</p>
```

## Anzeige & Sichtbarkeit

```html
<div class="d-flex gap-2">Flex-Container mit Abstand</div>
<div class="d-none d-md-block">Nur ab Tablet sichtbar</div>
<div class="w-100">Volle Breite</div>
```

## Karten (Cards)

```html
<div class="card">
    <div class="card-body">
        <h5 class="card-title">Titel</h5>
        <p class="card-text">Inhalt der Karte</p>
        <button class="btn btn-primary">Aktion</button>
    </div>
</div>
```

> **Das ist wichtig weil...** Mit diesen Hilfsklassen kannst du 80% der Abstände und Layouts direkt im HTML lösen — ohne eine einzige Zeile eigenes CSS zu schreiben.
