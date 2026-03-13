# Two-Way Binding

Daten fließen in beide Richtungen: Eingabe des Benutzers → C#-Variable → HTML-Anzeige.

## Beispiel mit @bind

```razor
<input @bind="name" />
<p>Du hast eingegeben: @name</p>

@code {
    private string name = "";
}
```

## @bind-Value für Formulare

```razor
<InputText @bind-Value="benutzer.Name" />
<InputNumber @bind-Value="benutzer.Alter" />
<InputCheckbox @bind-Value="benutzer.IstAktiv" />

@code {
    private Benutzer benutzer = new();
}
```

> **Das ist wichtig weil...** `@bind` ist das Standardwerkzeug für Formulareingaben in Blazor. Die Variable wird automatisch aktualisiert wenn der Benutzer tippt.
