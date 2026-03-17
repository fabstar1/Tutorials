# Das div-Element

`<div>` ist ein **Block-Container** ohne eigene Bedeutung. Es gruppiert andere Elemente, damit du sie gemeinsam gestalten oder positionieren kannst.

## Beispiel

```html
<div>
    <h2>Mein Bereich</h2>
    <p>Dieser Text gehört zum selben Block.</p>
</div>

<div>
    <p>Ein zweiter, unabhängiger Block.</p>
</div>
```

## div vs. span

| Element | Typ | Wann benutzen? |
|---------|-----|----------------|
| `<div>` | Block | Mehrere Elemente gruppieren (nimmt volle Breite ein) |
| `<span>` | Inline | Textteile innerhalb eines Absatzes markieren |

## Mit CSS kombiniert

```html
<div class="karte">
    <h3>Produktname</h3>
    <p>Kurze Beschreibung</p>
</div>
```

```css
.karte {
    border: 1px solid #ccc;
    padding: 16px;
    border-radius: 8px;
}
```

Das `<div>` bekommt durch die CSS-Klasse `karte` eine sichtbare Gestaltung — ohne die Klasse wäre es unsichtbar.

## In Blazor

In Blazor-Komponenten ist `<div>` das meistgenutzte Layout-Element:

```razor
<div class="container">
    <div class="row">
        <div class="col">
            <p>Inhalt</p>
        </div>
    </div>
</div>
```

> **Das ist wichtig weil...** `<div>` ist das Grundbaustein für jedes Layout. Ohne es kannst du Bereiche nicht unabhängig voneinander gestalten oder positionieren.
