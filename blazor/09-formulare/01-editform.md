# EditForm

`<EditForm>` ist Blazors Formular-Komponente. Sie verwaltet den Zustand des Formulars und ruft bei Absenden eine Methode auf.

## Komplettes Beispiel (direkt kopierbar)

Erstelle eine neue Datei z.B. `Components/Pages/BenutzerFormular.razor`:

```razor
@page "/benutzer-formular"
@using System.ComponentModel.DataAnnotations

<h2>Benutzer anlegen</h2>

<EditForm Model="benutzer" OnValidSubmit="Speichern">
    <DataAnnotationsValidator />

    <div class="mb-3">
        <label class="form-label">Name:</label>
        <InputText class="form-control" @bind-Value="benutzer.Name" />
        <ValidationMessage For="@(() => benutzer.Name)" class="text-danger" />
    </div>

    <div class="mb-3">
        <label class="form-label">Alter:</label>
        <InputNumber class="form-control" @bind-Value="benutzer.Alter" />
        <ValidationMessage For="@(() => benutzer.Alter)" class="text-danger" />
    </div>

    <button type="submit" class="btn btn-primary">Speichern</button>
</EditForm>

@if (gespeichert) {
    <div class="alert alert-success mt-3">Gespeichert: @benutzer.Name</div>
}

@code {
    private Benutzer benutzer = new();
    private bool gespeichert = false;

    private void Speichern() {
        // Hier später: await BenutzerService.SpeichernAsync(benutzer);
        gespeichert = true;
    }

    public class Benutzer {
        [Required(ErrorMessage = "Name ist erforderlich")]
        [StringLength(50, ErrorMessage = "Maximal 50 Zeichen")]
        public string Name { get; set; } = "";

        [Range(1, 120, ErrorMessage = "Alter muss zwischen 1 und 120 liegen")]
        public int Alter { get; set; }
    }
}
```

Die Seite ist unter `/benutzer-formular` erreichbar. Wenn du das Formular absendest, erscheint eine Erfolgsmeldung — ohne dass du einen Service brauchst.

> **Das ist wichtig weil...** `OnValidSubmit` wird nur aufgerufen wenn alle Validierungen bestanden wurden. Du musst nicht manuell prüfen ob Felder ausgefüllt sind.
