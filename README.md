# Interactive RGB Color Picker

A simple, single-file web application that allows users to pick colors using Red, Green, and Blue sliders and displays the corresponding hexadecimal color code.

## How to Use

1.  **Save the file:** Save the provided `index.html` content as `index.html` on your computer.
2.  **Open in browser:** Open the `index.html` file using any modern web browser (e.g., Chrome, Firefox, Safari, Edge).
3.  **Adjust sliders:** Manipulate the Red, Green, and Blue sliders to change the color displayed in the circle.
4.  **View output:** The current color will be shown in the circular display, and its corresponding hexadecimal code will be automatically updated in the "HEX" output field.

## Code Explanation

This project is implemented entirely within a single `index.html` file, leveraging HTML, CSS, and vanilla JavaScript.

### HTML

The HTML structure defines the user interface:
*   A main `div` container for layout.
*   A `h1` title for the application.
*   A `div` with the ID `colorDisplay` that acts as the visual representation of the selected color.
*   Three `div` elements, each containing:
    *   A `label` (R, G, B).
    *   An `input type="range"` slider (`id="redSlider"`, `id="greenSlider"`, `id="blueSlider"`) with a range from 0 to 255.
    *   A `span` (`id="redValue"`, etc.) to display the current numeric value of each slider.
*   A `div` for the hexadecimal output, containing a `label` and a `readonly input type="text"` (`id="hexOutput"`) to display the calculated hex code.

### CSS

The inline CSS provides basic styling for a clean and user-friendly appearance:
*   Centers the content vertically and horizontally.
*   Styles the `container` with a white background, padding, rounded corners, and a subtle shadow.
*   Customizes the appearance of the `input type="range"` sliders for better visual feedback, including distinct thumb colors for R, G, B.
*   Styles the `color-display` as a prominent circle.
*   Ensures the hex output field is clearly visible and non-editable.

### JavaScript

The vanilla JavaScript code provides the interactivity:
*   **DOM Element References:** It first retrieves references to all necessary HTML elements (sliders, value displays, color display, hex output) using their `id`s.
*   **`componentToHex(c)` Function:** A helper function that takes a decimal color component (0-255) and converts it into a two-digit hexadecimal string (e.g., 255 -> "FF", 0 -> "00", 10 -> "0A").
*   **`rgbToHex(r, g, b)` Function:** Takes three decimal RGB values and combines them using `componentToHex` to return a full hexadecimal color string (e.g., "#RRGGBB").
*   **`updateColor()` Function:**
    *   Reads the current values from the Red, Green, and Blue sliders.
    *   Updates the `span` elements next to each slider to show the current numeric RGB values.
    *   Sets the `backgroundColor` of the `colorDisplay` `div` using the `rgb()` CSS function.
    *   Calls `rgbToHex` to get the hexadecimal representation and updates the `value` of the `hexOutput` input field.
*   **Event Listeners:** `input` event listeners are attached to each slider. Every time a slider's value changes, the `updateColor()` function is called, ensuring real-time updates of the color display and hex output.
*   **Initial State:** An initial call to `updateColor()` is made when the script loads to set the initial color (black) and hex output.

## License

This project is licensed under the MIT License.