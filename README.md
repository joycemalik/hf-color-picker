# Interactive RGB Color Picker

A simple, single-file web application that provides an interactive color picker experience. Users can adjust Red, Green, and Blue (RGB) sliders to mix colors, see the resulting color swatch, and get the corresponding hexadecimal (HEX) color code.

## How to Use

1.  **Save the file:** Save the provided `index.html` content as `index.html` on your computer.
2.  **Open in browser:** Open the `index.html` file using any modern web browser (e.g., Chrome, Firefox, Safari, Edge).
3.  **Adjust sliders:** Drag the Red, Green, and Blue sliders to change their respective values (from 0 to 255).
4.  **Observe changes:** The central color swatch will instantly update to reflect the chosen RGB combination, and the hexadecimal color code will be displayed in the HEX output field.

## Code Explanation

This project is implemented within a single `index.html` file, leveraging HTML, CSS, and vanilla JavaScript.

### HTML Structure (`index.html`)

*   **`color-picker-container`**: A main `div` acts as a container for all elements of the color picker, providing a clean layout.
*   **`h1`**: Displays the title "Color Picker".
*   **`color-display`**: A `div` element styled to display the current color, dynamically updated by JavaScript.
*   **`slider-group`**: Three separate `div`s, each containing:
    *   A `label` for "R", "G", or "B".
    *   An `input type="range"` slider with `min="0"` and `max="255"` to control the intensity of each color component.
    *   A `span` to display the current numeric value of the corresponding slider.
*   **`hex-output`**: A `div` containing:
    *   A `label` for "HEX".
    *   An `input type="text"` field (`readonly`) that displays the hexadecimal representation of the current color.

### CSS Styling (`<style>` tag in `index.html`)

*   The CSS is embedded directly in the `<head>` section.
*   It provides basic styling for a clean and modern look:
    *   Centers the color picker on the page.
    *   Styles the container with a shadow and rounded corners.
    *   Defines the dimensions and border for the `color-display` swatch.
    *   Applies styles to the range input sliders, including custom thumb appearances for better usability and visual feedback (different colors for R, G, B thumbs).
    *   Formats the value `span`s and the `hex-output` input field.

### JavaScript Logic (`<script>` tag in `index.html`)

*   The JavaScript is embedded at the end of the `<body>` for optimal page loading.
*   **DOM Element Selection**: It first selects all necessary HTML elements (sliders, value spans, color display, hex input) using `document.getElementById` and `document.querySelector`.
*   **`rgbToHex(r, g, b)` function**:
    *   Takes three integer arguments (red, green, blue values).
    *   Includes a helper `toHex` function to convert a single color component to a two-digit hexadecimal string (e.g., 255 becomes "ff", 0 becomes "00").
    *   Ensures color values are clamped between 0 and 255.
    *   Returns the full hex color code prefixed with "#".
*   **`updateColor()` function**:
    *   Reads the current values from the Red, Green, and Blue sliders.
    *   Updates the `textContent` of the `span` elements next to each slider to display the numeric value.
    *   Sets the `background-color` of the `color-display` div using the `rgb()` CSS function.
    *   Calls `rgbToHex()` to convert the current RGB values into a hex string.
    *   Updates the `value` of the `hexInput` field with the generated hex code.
*   **Event Listeners**: `input` event listeners are attached to each of the three range sliders (`redSlider`, `greenSlider`, `blueSlider`). Whenever a slider's value changes, the `updateColor()` function is called.
*   **Initial Call**: `updateColor()` is called once on page load to initialize the color display and hex output with the default slider values (which are all 0, resulting in black).

## License

This project is licensed under the MIT License.