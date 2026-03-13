# Bedingungen & Schleifen

## Bedingungen

```csharp
int alter = 20;

if (alter >= 18) {
    Console.WriteLine("Volljährig");
}
else {
    Console.WriteLine("Minderjährig");
}
```

## Schleifen

```csharp
// for-Schleife
for (int i = 0; i < 5; i++) {
    Console.WriteLine(i);
}

// foreach-Schleife (für Listen)
var namen = new List<string> { "Anna", "Ben", "Clara" };
foreach (var name in namen) {
    Console.WriteLine(name);
}
```

> **Das ist wichtig weil...** In Blazor nutzt du `@if` und `@foreach` direkt im HTML-Teil der Komponente. Die C#-Syntax ist exakt dieselbe.
