# Validierung

Validierungsregeln werden direkt am Modell mit Attributen definiert.

## Modell mit Validierung

```csharp
using System.ComponentModel.DataAnnotations;

public class Benutzer {
    [Required(ErrorMessage = "Name ist erforderlich")]
    [StringLength(50, ErrorMessage = "Maximal 50 Zeichen")]
    public string Name { get; set; } = "";

    [Range(0, 120, ErrorMessage = "Alter muss zwischen 0 und 120 liegen")]
    public int Alter { get; set; }

    [Required]
    [EmailAddress(ErrorMessage = "Keine gültige E-Mail")]
    public string Email { get; set; } = "";
}
```

## Wichtige Validierungsattribute

| Attribut | Bedeutung |
|----------|-----------|
| `[Required]` | Pflichtfeld |
| `[StringLength(max)]` | Maximale Länge |
| `[Range(min, max)]` | Zahlenbereich |
| `[EmailAddress]` | E-Mail-Format |
| `[MinLength(n)]` | Mindestlänge |

> **Das ist wichtig weil...** Die Validierungslogik sitzt einmal im Modell und gilt überall — im Formular, beim Speichern, in der API.
