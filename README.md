[English](https://github.com/gbe-brokers/risk-warning/blob/main/README_en.md) 👈

# So fügen Sie das Risikowarnungs-Widget zu Ihrer Website hinzu

Es gibt zwei Möglichkeiten, die Risikowarnung zu integrieren: als **iFrame-Widget** oder als **JSON-API**.

---

## Option 1: iFrame-Widget

1. **Kopieren Sie den iframe-Code:**

   ```html
   <iframe
     src="https://gbebrokers.com/api/risk_warning/"
     width="100%"
     height="100"
     frameborder="0"
     style="border:0;"
   ></iframe>
   ```

2. **Passen Sie das Widget an:**

   Sie können das Erscheinungsbild, die Sprache und die Textlänge des Widgets anpassen, indem Sie URL-Parameter hinzufügen. Hier sind die verfügbaren Parameter:

   | Parameter  | Beschreibung                               | Verfügbare Optionen                                                                 | Standardwert        |
   | ---------- | ------------------------------------------ | ----------------------------------------------------------------------------------- | ------------------- |
   | `language` | Sprache der Risikowarnung                  | `de` = Deutsch, `en` = Englisch                                                     | `de`                |
   | `font`     | Schriftfamilie für den Text                | Jeder gültige CSS-`font-family`-Wert, z. B. `Arial`, `Verdana`, `Arial, sans-serif` | `Arial, sans-serif` |
   | `fontSize` | Schriftgröße für den Text                  | Jeder gültige CSS-`font-size`-Wert, z. B. `1rem`, `16px`, `1.2em`                   | `1rem`              |
   | `color`    | Textfarbe                                  | Jeder gültige CSS-Farbwert, z. B. `black`, `#ff0000`, `rgb(255,0,0)`                | `black`             |
   | `bgColor`  | Hintergrundfarbe der Risikowarnung         | Jeder gültige CSS-Farbwert, z. B. `white`, `#ffff00`, `rgb(255,255,0)`              | `white`             |
   | `short`    | Zeigt die Kurzversion der Risikowarnung an | `true`, `1`, `yes`, `on`                                                            | Volltext            |

   **Beispiel:**

   ```html
   <iframe
     src="https://gbebrokers.com/api/risk_warning/?language=en&font=Verdana&color=red&bgColor=yellow&fontSize=15px"
     width="100%"
     height="100"
     frameborder="0"
     style="border:0;"
   ></iframe>
   ```

3. **Fügen Sie den iframe auf Ihrer Website ein:**
   - Fügen Sie den iframe-Code an der Stelle in den HTML-Code ein, an der das Widget erscheinen soll.
   - Passen Sie die Attribute `width` und `height` an den verfügbaren Bereich in Ihrem Layout an.

---

## Option 2: JSON-API

Wenn Sie den Risikohinweistext selbst rendern möchten, können Sie die JSON-API verwenden.

**Endpunkt:**
`GET https://gbebrokers.com/api/risk_warning/json`

**Unterstützte Parameter:**

| Parameter  | Beschreibung                           | Verfügbare Optionen             | Standardwert |
| ---------- | -------------------------------------- | ------------------------------- | ------------ |
| `language` | Sprache der Risikowarnung              | `de` = Deutsch, `en` = Englisch | `de`         |
| `short`    | Gibt die Kurzversion des Textes zurück | `true`, `1`, `yes`, `on`        | Volltext     |

**Beispielanfrage:**
`GET https://gbebrokers.com/api/risk_warning/json?language=en&short=true`

**Beispielantwort:**

```json
{
  "success": true,
  "data": {
    "language": "en",
    "variant": "short",
    "percentage": "73.62",
    "text": "73.62% of retail investor accounts lose money"
  }
}
```

**Vollständige deutsche Antwort (Standard):**

```json
{
  "success": true,
  "data": {
    "language": "de",
    "variant": "full",
    "percentage": "73,62",
    "text": "Traden Sie verantwortungsvoll: CFDs sind komplexe Instrumente und bergen ein hohes Risiko, Gelder schnell durch Hebelwirkung zu verlieren. 73,62% der Privatanleger-Konten verlieren Gelder, wenn Sie CFDs mit diesem Anbieter handeln. Sie sollten überlegen, ob Sie verstehen, wie CFDs funktionieren und ob Sie es sich leisten können, das Risiko einzugehen, Ihr Geld zu verlieren."
  }
}
```

## Beispiel-Integrationen (iFrame)

### Vollständige englische Version

```html
<iframe
  src="https://gbebrokers.com/api/risk_warning/?language=en&font=Verdana&color=white&bgColor=%23ff6600&fontSize=1.2rem"
  width="100%"
  height="100"
  frameborder="0"
  style="border:0;"
></iframe>
```

### Kurze englische Version

```html
<iframe
  src="https://gbebrokers.com/api/risk_warning/?language=en&short=true"
  width="100%"
  height="60"
  frameborder="0"
  style="border:0;"
></iframe>
```

Ausgabe:

```text
XX.XX% of retail investor accounts lose money
```

### Kurze deutsche Version

```html
<iframe
  src="https://gbebrokers.com/api/risk_warning/?language=de&short=true"
  width="100%"
  height="60"
  frameborder="0"
  style="border:0;"
></iframe>
```

Ausgabe:

```text
XX,XX % der Konten von Kleinanlegern verlieren Geld
```

---

## Hinweise

- Passen Sie die iframe-Abmessungen (`width` und `height`) nach Bedarf an Ihr Layout an.
- Wenn keine Parameter angegeben werden, ist die Standardsprache Deutsch (`de`), und die Standardstile werden verwendet.
- Wenn `short` nicht angegeben wird, wird die vollständige Version der Risikowarnung angezeigt.
- Wenn Sie Hex-Farbcodes in der URL verwenden, stellen Sie sicher, dass diese URL-codiert sind, zum Beispiel `%23ff6600` statt `#ff6600`.
- Die `font`-, `fontSize`-, `color`- und `bgColor`-Parameter gelten nur für das iFrame-Widget und werden von der JSON-API ignoriert.
