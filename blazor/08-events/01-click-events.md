# Click Events & andere DOM-Events

## Button-Klick

```razor
<button @onclick="HandleKlick">Klick mich</button>
<p>Geklickt: @anzahl Mal</p>

@code {
    private int anzahl = 0;

    private void HandleKlick() {
        anzahl++;
    }
}
```

## Mit Event-Parameter

```razor
<button @onclick="HandleKlick">Klick</button>

@code {
    private void HandleKlick(MouseEventArgs e) {
        Console.WriteLine($"Klick bei X={e.ClientX}");
    }
}
```

## Weitere Events

```razor
<input @oninput="HandleInput" />
<input @onkeydown="HandleTaste" />
<div @onmouseover="HandleHover">Hover über mich</div>
```

> **Das ist wichtig weil...** `@onclick` ist der häufigste Event in Blazor. Das Muster ist immer gleich: Event-Direktive + Methodenname.
