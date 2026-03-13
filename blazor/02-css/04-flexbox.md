# Flexbox

Flexbox ist das einfachste CSS-Layout-System für Zeilen und Spalten.

## Beispiel

```css
.container {
    display: flex;                  /* Flexbox aktivieren */
    flex-direction: row;            /* Elemente nebeneinander (Standard) */
    justify-content: space-between; /* Horizontal verteilen */
    align-items: center;            /* Vertikal zentrieren */
    gap: 16px;                      /* Abstand zwischen Elementen */
}
```

```html
<div class="container">
    <div>Links</div>
    <div>Mitte</div>
    <div>Rechts</div>
</div>
```

| Eigenschaft | Werte (Auswahl) |
|-------------|-----------------|
| `flex-direction` | `row`, `column` |
| `justify-content` | `flex-start`, `center`, `space-between` |
| `align-items` | `flex-start`, `center`, `stretch` |

> **Das ist wichtig weil...** Blazor-Layouts bestehen oft aus Navigationsleiste + Inhalt nebeneinander. Flexbox ist dafür die einfachste Lösung.
