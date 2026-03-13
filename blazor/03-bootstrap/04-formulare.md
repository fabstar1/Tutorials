# Formulare

Bootstrap stylt Formulare mit der Klasse `form-control` für Eingabefelder und `form-label` für Beschriftungen.

## Beispiel

```html
<div class="mb-3">
    <label class="form-label">Name</label>
    <input type="text" class="form-control" placeholder="Dein Name" />
</div>

<div class="mb-3">
    <label class="form-label">E-Mail</label>
    <input type="email" class="form-control" />
</div>

<div class="mb-3">
    <label class="form-label">Land</label>
    <select class="form-select">
        <option>Deutschland</option>
        <option>Österreich</option>
    </select>
</div>

<div class="mb-3 form-check">
    <input type="checkbox" class="form-check-input" id="agb" />
    <label class="form-check-label" for="agb">AGB akzeptieren</label>
</div>

<button class="btn btn-primary">Absenden</button>
```

## In Blazor mit EditForm

```razor
<EditForm Model="benutzer" OnValidSubmit="Speichern">
    <DataAnnotationsValidator />

    <div class="mb-3">
        <label class="form-label">Name</label>
        <InputText class="form-control" @bind-Value="benutzer.Name" />
        <ValidationMessage For="@(() => benutzer.Name)" class="text-danger" />
    </div>

    <button type="submit" class="btn btn-primary">Speichern</button>
</EditForm>
```

> **Das ist wichtig weil...** `form-control` macht alle Eingabefelder einheitlich breit und gut lesbar. `mb-3` (margin-bottom) sorgt für den richtigen Abstand zwischen den Feldern.
