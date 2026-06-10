[Deutsch](https://github.com/gbe-brokers/risk-warning/blob/main/README.md) 👈

# How to Add the Risk Warning Widget to Your Website

There are two ways to integrate the risk warning: as an **iFrame widget** or as a **JSON API**.

---

## Option 1: iFrame Widget

1. **Copy the iframe code:**

   ```html
   <iframe
     src="https://gbebrokers.com/api/risk_warning/"
     width="100%"
     height="100"
     frameborder="0"
     style="border:0;"
   ></iframe>
   ```

2. **Customize the widget:**

   You can customize the widget's appearance, language, and text length by adding URL parameters. Here are the available parameters:

   | Parameter  | Description                                         | Available Options                                                               | Default Value       |
   | ---------- | --------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------- |
   | `language` | Language of the risk warning message                | `de` = German, `en` = English                                                   | `de`                |
   | `font`     | Font family for the text                            | Any valid CSS `font-family` value, e.g. `Arial`, `Verdana`, `Arial, sans-serif` | `Arial, sans-serif` |
   | `fontSize` | Font size for the text                              | Any valid CSS `font-size` value, e.g. `1rem`, `16px`, `1.2em`                   | `1rem`              |
   | `color`    | Text color                                          | Any valid CSS color value, e.g. `black`, `#ff0000`, `rgb(255,0,0)`              | `black`             |
   | `bgColor`  | Background color of the risk warning message        | Any valid CSS color value, e.g. `white`, `#ffff00`, `rgb(255,255,0)`            | `white`             |
   | `short`    | Displays the short version of the risk warning text | `true`, `1`, `yes`, `on`                                                        | Full text           |

   **Example:**

   ```html
   <iframe
     src="https://gbebrokers.com/api/risk_warning/?language=en&font=Verdana&color=red&bgColor=yellow&fontSize=15px"
     width="100%"
     height="100"
     frameborder="0"
     style="border:0;"
   ></iframe>
   ```

3. **Add the iframe to your website:**
   - Insert the iframe code into the HTML where you want the widget to appear.
   - Adjust the `width` and `height` attributes to fit the available area in your layout.

---

## Option 2: JSON API

If you prefer to fetch the risk warning text and render it yourself, use the JSON API.

**Endpoint:**
`GET https://gbebrokers.com/api/risk_warning/json`

**Supported parameters:**

| Parameter  | Description                           | Available Options             | Default Value |
| ---------- | ------------------------------------- | ----------------------------- | ------------- |
| `language` | Language of the risk warning          | `de` = German, `en` = English | `de`          |
| `short`    | Returns the short version of the text | `true`, `1`, `yes`, `on`      | Full text     |

**Example request:**
`GET https://gbebrokers.com/api/risk_warning/json?language=en&short=true`

**Example response:**

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

**Full German response (default):**

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

---

## Example Integrations (iFrame)

### Full English version

```html
<iframe
  src="https://gbebrokers.com/api/risk_warning/?language=en&font=Verdana&color=white&bgColor=%23ff6600&fontSize=1.2rem"
  width="100%"
  height="100"
  frameborder="0"
  style="border:0;"
></iframe>
```

### Short English version

```html
<iframe
  src="https://gbebrokers.com/api/risk_warning/?language=en&short=true"
  width="100%"
  height="60"
  frameborder="0"
  style="border:0;"
></iframe>
```

Output:

```text
XX.XX% of retail investor accounts lose money
```

### Short German version

```html
<iframe
  src="https://gbebrokers.com/api/risk_warning/?language=de&short=true"
  width="100%"
  height="60"
  frameborder="0"
  style="border:0;"
></iframe>
```

Output:

```text
XX,XX % der Konten von Kleinanlegern verlieren Geld
```

---

## Notes

- Customize the iframe dimensions (`width` and `height`) as needed to fit your layout.
- If no parameters are provided, the default language is German (`de`), and default styles are applied.
- If `short` is not provided, the full version of the risk warning is shown.
- If you use hex color codes in the URL, make sure they are URL-encoded, for example `%23ff6600` instead of `#ff6600`.
- The `font`, `fontSize`, `color`, and `bgColor` parameters apply to the iFrame widget only and are ignored by the JSON API.
