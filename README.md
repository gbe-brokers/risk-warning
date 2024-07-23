[English](https://github.com/gbe-brokers/risk-warning/blob/main/README_en.md) 👈

# So fügen Sie die Risikowarnung zu Ihrer Website hinzu

1.  **Kopieren Sie diesen HTML iframe tag:**

    ```html
    <iframe
      src="https://gbebrokers.com/api/risk_warning/"
      width="100%"
      height="100"
      frameborder="0"
      style="border:0;"
    ></iframe>
    ```

2.  **Passen Sie das Widget an:**

    Sie können das Aussehen und die Sprache des Widgets anpassen, indem Sie URL Parameter hinzufügen. Hier sind die verfügbaren Parameter:

    | Parameter  | Beschreibung                       | Verfügbare Optionen                                                                                                                                                                                                                                                                                                | Standardwert        |
    | ---------- | ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------- |
    | `lang`     | Sprache der Risikowarnung          | <table> <thead> <tr> <th>code</th> <th>Sprache</th> </tr> </thead> <tbody> <tr> <td><code>de</code></td> <td>Deutsch</td> </tr> <tr> <td><code>en</code></td> <td>Englisch</td> </tr> <tr> <td><code>es</code></td> <td>Spanisch</td> </tr><tr> <td><code>ar</code></td> <td>Arabisch</td> </tr> </tbody> </table> | `de` - Deutsch      |
    | `font`     | Schriftfamilie für den Text        | Jeder gültige CSS Schriftfamilie Family Wert, bspw. `Arial`, `Verdana`                                                                                                                                                                                                                                             | `Arial, sans-serif` |
    | `fontSize` | Schriftgröße                       | Jeder gültige CSS-Wert für die Schriftgröße, bspw. `1rem`, `16px`, `1.2em`                                                                                                                                                                                                                                         | `1rem`              |
    | `color`    | Textfarbe                          | Jeder gültige CSS-Farbwert, bspw. `black`, `#ff0000`, `rgb(255,0,0)`                                                                                                                                                                                                                                               | `black`             |
    | `bgColor`  | Hintergrundfarbe der Risikowarnung | Jeder gültige CSS-Farbwert, bspw. `white`, `#ffff00`, `rgb(255,255,0)`                                                                                                                                                                                                                                             | `black`             |

    **Beispiel:**

    ```html
    <iframe
      src="https://gbebrokers.com/api/risk_warning/?lang=en&font=Verdana&color=red&bgColor=yellow&fontSize=15px"
      width="100%"
      height="100"
      frameborder="0"
      style="border:0;"
    ></iframe>
    ```

3.  **Den iframe auf Ihrer Website einfügen:**

    - Fügen Sie den Iframe-Code an der Stelle in den HTML-Code ein, an der das Widget auf Ihrer Website erscheinen soll.
    - Passen Sie die Attribute für Breite (`width`) und Höhe (`height`) des iframe so an, dass er in den gewünschten Bereich Ihrer Webseite passt.

## Beispiel für die Integration:

Das Widget wird auf `https://gbebrokers.com/api/risk_warning/` gehostet. Wenn Sie es in englischer Sprache mit angepassten Stilen wünschen:

```html
<iframe
  src="https://gbebrokers.com/api/risk_warning/?lang=en&font=Verdana&color=white&bgColor=%23ff6600&fontSize=1.2rem"
  width="100%"
  height="100"
  frameborder="0"
  style="border:0;"
></iframe>
```

### Anmerkungen:

- Passen Sie die Abmessungen des iframe `width` (Breite) und `height` (Höhe) nach Bedarf an Ihr Layout an.
- Wenn keine Parameter angegeben werden, ist die Standardsprache Deutsch (de), und es werden die Standardstile verwendet (Schriftart Arial, schwarze Textfarbe, weiße Hintergrundfarbe und Schriftgröße 1rem).
- • Wenn Sie Hex-Codes für Farben verwenden, stellen Sie sicher, dass diese URL-codiert sind (z. B. verwenden Sie `%23ff6600` statt `#ff6600`).
