# HTML Formulare

Formulare ermöglichen Benutzereingaben. In Blazor ersetzt du das Standard-HTML-Formular meistens durch `<EditForm>` — das Grundprinzip bleibt aber gleich.

## Beispiel

```html
<form>
    <label for="name">Name:</label>
    <input type="text" id="name" placeholder="Dein Name" />

    <label for="email">E-Mail:</label>
    <input type="email" id="email" />

    <input type="checkbox" id="agb" />
    <label for="agb">AGB akzeptieren</label>

    <select id="land">
        <option value="de">Deutschland</option>
        <option value="at">Österreich</option>
    </select>

    <button type="submit">Absenden</button>
</form>
```

| Element | Bedeutung |
|---------|-----------|
| `<input type="text">` | Einzeiliges Textfeld |
| `<input type="email">` | E-Mail-Feld mit Validierung |
| `<input type="checkbox">` | Checkbox |
| `<select>` | Dropdown-Liste |
| `<button type="submit">` | Absende-Schaltfläche |

> **Das ist wichtig weil...** Blazor's `<EditForm>` baut auf diesen Elementen auf. Wer HTML-Formulare versteht, versteht auch, was Blazor im Hintergrund erzeugt.
