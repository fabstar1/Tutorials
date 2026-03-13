# Bilder & Links

## Links

```html
<!-- Externer Link -->
<a href="https://dotnet.microsoft.com" target="_blank">Microsoft .NET</a>

<!-- Interner Link -->
<a href="/counter">Zur Counter-Seite</a>
```

## Bilder

```html
<img src="images/logo.png" alt="Firmenlogo" width="200" />
```

| Attribut | Bedeutung |
|----------|-----------|
| `href` | Ziel-URL des Links |
| `target="_blank"` | In neuem Tab öffnen |
| `src` | Pfad zum Bild |
| `alt` | Alternativer Text (Barrierefreiheit) |

> **Das ist wichtig weil...** In Blazor navigierst du intern mit dem `<NavLink>` Komponenten — aber das zugrundeliegende HTML-Konzept ist identisch mit `<a href>`.
