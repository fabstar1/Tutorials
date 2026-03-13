# CSS Selektoren

Mit Selektoren wählst du aus, welche HTML-Elemente gestylt werden sollen.

## Beispiel

```css
/* Element-Selektor: alle <p> */
p {
    color: black;
}

/* Klassen-Selektor: alle mit class="hinweis" */
.hinweis {
    background-color: yellow;
}

/* ID-Selektor: das Element mit id="titel" */
#titel {
    font-size: 2rem;
}

/* Kombination: <p> innerhalb von .card */
.card p {
    margin: 8px;
}
```

| Selektor | Bedeutung |
|----------|-----------|
| `p` | Alle `<p>`-Elemente |
| `.klasse` | Alle Elemente mit dieser Klasse |
| `#id` | Das Element mit dieser ID |

> **Das ist wichtig weil...** In Blazor-Komponenten nutzt du fast immer Klassen-Selektoren. IDs solltest du sparsam verwenden, da sie einmalig sein müssen.
