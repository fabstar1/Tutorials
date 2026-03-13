# CSS Grundlagen

CSS (Cascading Style Sheets) bestimmt das **Aussehen** deiner Webseite — Farben, Abstände, Schriften, Layouts.

## Warum CSS?

Ohne CSS musst du jeden Style direkt am HTML-Element schreiben — das wird schnell unübersichtlich:

```html
<!-- Ohne CSS: Inline Styles direkt am Element -->
<div style="background-color: #4a90d9; color: white; padding: 16px; border-radius: 8px;
            font-size: 18px; font-weight: bold; margin-bottom: 12px; box-shadow: 0 2px 4px rgba(0,0,0,0.2);">
    Meine Überschrift
</div>
<div style="background-color: #4a90d9; color: white; padding: 16px; border-radius: 8px;
            font-size: 18px; font-weight: bold; margin-bottom: 12px; box-shadow: 0 2px 4px rgba(0,0,0,0.2);">
    Noch eine Überschrift
</div>
```

Wenn du die Farbe ändern willst, musst du **jedes einzelne Element** anfassen. Mit einer CSS-Klasse schreibst du den Style **einmal** und verwendest ihn überall:

```html
<!-- Mit CSS-Klasse: Style einmal definieren, überall nutzen -->
<style>
    .karten-titel {
        background-color: #4a90d9;
        color: white;
        padding: 16px;
        border-radius: 8px;
        font-size: 18px;
        font-weight: bold;
        margin-bottom: 12px;
        box-shadow: 0 2px 4px rgba(0,0,0,0.2);
    }
</style>

<div class="karten-titel">Meine Überschrift</div>
<div class="karten-titel">Noch eine Überschrift</div>
```

Jetzt reicht eine einzige Änderung in `.karten-titel` um alle Überschriften anzupassen.

## Themen

- [Selektoren](./01-selektoren.md)
- [Box-Modell](./02-box-modell.md)
- [Farben & Schriften](./03-farben-schriften.md)
- [Flexbox](./04-flexbox.md)
- [Klassen & IDs](./05-klassen-ids.md)

> **Das ist wichtig weil...** Blazor-Komponenten haben kein eigenes Styling-System. Du schreibst CSS wie gewohnt, entweder global oder in `.razor.css`-Dateien pro Komponente.
