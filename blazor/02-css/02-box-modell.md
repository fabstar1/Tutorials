# Das Box-Modell

Jedes HTML-Element ist eine Box. Das Box-Modell beschreibt, wie Inhalt, Innenabstand, Rahmen und Außenabstand zusammenspielen.

## Visualisierung

```
+-------------------------+
|       margin            |  ← Außenabstand (unsichtbar)
|  +-------------------+  |
|  |     border        |  |  ← Rahmen
|  |  +-------------+  |  |
|  |  |   padding   |  |  |  ← Innenabstand
|  |  | +---------+ |  |  |
|  |  | | content | |  |  |  ← Inhalt
|  |  | +---------+ |  |  |
|  |  +-------------+  |  |
|  +-------------------+  |
+-------------------------+
```

## Beispiel

```css
.karte {
    margin: 16px;           /* Außenabstand */
    padding: 12px;          /* Innenabstand */
    border: 1px solid gray; /* Rahmen */
    width: 300px;           /* Breite des Inhalts */
    box-sizing: border-box; /* Breite inkl. padding + border */
}
```

> **Das ist wichtig weil...** Abstände und Ausrichtungen in Blazor-Layouts werden fast immer über `margin` und `padding` gesteuert. `box-sizing: border-box` ist heute Standard und erspart viele Überraschungen.
