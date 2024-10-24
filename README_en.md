[Deutsch](https://github.com/gbe-brokers/risk-warning/blob/main/README.md) 👈

# How to Add the Risk Warning Widget to Your Website

1.  **Copy the iframe code:**

    ```html
    <iframe
      src="https://gbebrokers.com/api/risk_warning/"
      width="100%"
      height="100"
      frameborder="0"
      style="border:0;"
    ></iframe>
    ```

2.  **Customize the Widget:**

    You can customize the widget's appearance and language by adding URL parameters. Here are the available parameters:

    | Parameter  | Description                                  | Available Options                                                                                                                                                                                      | Default Value       |
    | ---------- | -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------- |
    | `lang`     | Language of the risk warning message         | <table> <thead> <tr> <th>code</th> <th>Language</th> </tr> </thead> <tbody> <tr> <td><code>de</code></td> <td>German</td> </tr> <tr> <td><code>en</code></td> <td>English</td> </tr> </tbody> </table> | `de` - German       |
    | `font`     | Font family for the text                     | Any valid CSS font-family value, e.g., `Arial`, `Verdana`                                                                                                                                              | `Arial, sans-serif` |
    | `fontSize` | Font size for the text                       | Any valid CSS font-size value, e.g., `1rem`, `16px`, `1.2em`                                                                                                                                           | `1rem`              |
    | `color`    | Text color                                   | Any valid CSS color value, e.g., `black`, `#ff0000`, `rgb(255,0,0)`                                                                                                                                    | `black`             |
    | `bgColor`  | Background color of the risk warning message | Any valid CSS color value, e.g., `white`, `#ffff00`, `rgb(255,255,0)`                                                                                                                                  | `black`             |

    **Example:**

    ```html
    <iframe
      src="https://gbebrokers.com/api/risk_warning/?lang=en&font=Verdana&color=red&bgColor=yellow&fontSize=15px"
      width="100%"
      height="100"
      frameborder="0"
      style="border:0;"
    ></iframe>
    ```

3.  **Add the iframe to Your Website:**

    - Insert the iframe code into the HTML where you want the widget to appear on your website.
    - Adjust the `width` and `height` attributes of the iframe to fit the desired area on your webpage.

## Example Integration:

The widget is hosted at `https://gbebrokers.com/api/risk_warning/`. If you want it in English with customized styles:

```html
<iframe
  src="https://gbebrokers.com/api/risk_warning/?lang=en&font=Verdana&color=white&bgColor=%23ff6600&fontSize=1.2rem"
  width="100%"
  height="100"
  frameborder="0"
  style="border:0;"
></iframe>
```

### Notes:

- Customize the iframe dimensions (`width` and `height`) as needed to fit your layout.
- If no parameters are provided, the default language will be German (`de`), and default styles will be applied (Arial font, black text color, white background color, and 1rem font size).
- If you use hex codes for colors, ensure they are URL-encoded (e.g., use `%23ff6600` instead of `#ff6600`).
