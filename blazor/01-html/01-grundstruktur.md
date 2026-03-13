# HTML Grundstruktur

Eine HTML-Seite besteht aus einem festen Grundgerüst. Blazor-Seiten nutzen dieses Gerüst intern automatisch — es hilft aber zu verstehen, wie es aufgebaut ist.

## Aufbau

```html
<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <title>Meine Seite</title>
</head>
<body>
    <h1>Hallo Welt</h1>
    <p>Das ist mein erster Inhalt.</p>
</body>
</html>
```

| Tag | Bedeutung |
|-----|-----------|
| `<!DOCTYPE html>` | Teilt dem Browser mit: das ist HTML5 |
| `<html>` | Wurzelelement der Seite |
| `<head>` | Metadaten (Titel, Zeichensatz usw.) |
| `<body>` | Sichtbarer Inhalt der Seite |

> **Das ist wichtig weil...** Alle sichtbaren Inhalte müssen im `<body>` stehen. In Blazor-Komponenten schreibst du nur den `<body>`-Inhalt — das Grundgerüst übernimmt Blazor für dich.
