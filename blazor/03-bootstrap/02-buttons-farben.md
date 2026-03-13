# Buttons & Farben

Bootstrap hat ein einheitliches Farbsystem mit vorgefertigten Klassen.

## Buttons

```html
<button class="btn btn-primary">Primär (Blau)</button>
<button class="btn btn-secondary">Sekundär (Grau)</button>
<button class="btn btn-success">Erfolg (Grün)</button>
<button class="btn btn-danger">Gefahr (Rot)</button>
<button class="btn btn-warning">Warnung (Gelb)</button>
<button class="btn btn-outline-primary">Nur Rahmen</button>

<!-- Größen -->
<button class="btn btn-primary btn-sm">Klein</button>
<button class="btn btn-primary btn-lg">Groß</button>
```

## Farbklassen (für Hintergründe und Text)

```html
<div class="bg-primary text-white p-3">Blauer Hintergrund</div>
<div class="bg-success text-white p-3">Grüner Hintergrund</div>
<div class="bg-danger text-white p-3">Roter Hintergrund</div>
<div class="bg-light text-dark p-3">Heller Hintergrund</div>
```

## In Blazor

```razor
<button class="btn btn-primary" @onclick="Speichern">Speichern</button>
<button class="btn btn-danger" @onclick="Löschen">Löschen</button>
<button class="btn btn-secondary" @onclick="Abbrechen">Abbrechen</button>
```

> **Das ist wichtig weil...** Einheitliche Farben (Blau = Aktion, Rot = Löschen, Grün = Erfolg) helfen Benutzern, die Oberfläche intuitiv zu verstehen.
