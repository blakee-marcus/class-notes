# Colors in CSS

## Link a CSS File to an HTML file

### 1. Creating a CSS file:
First, create a CSS file. Let's name it `styles.css`. Save this file in the same directory as your HTML file.

### 2. Linking the CSS file to your HTML file:
Open your HTML file. Inside the `<head>` section of your HTML file, you will insert a `<link>` element to connect the two files. The syntax is as follows:

```html
<link rel="stylesheet" href="styles.css">
```

### 3. Explanation of the attributes in the <link> element:

- `rel`: This specifies the relationship between the current file and the linked file. In this case, the relationship is a "stylesheet."
- `href`: This is the path to your CSS file. If the CSS file is in the same directory as your HTML file, just the filename is enough. However, if it's in a different folder or location, you'd need to provide the relative or absolute path.

### Example:
Let's say your folder structure looks like this:

```bash
/my_website/
├── index.html
└── /css/
    └── styles.css
```

If you want to link the `styles.css` from the `css` folder to your index.html, the `<link>` element would look like this:

```html
<link rel="stylesheet" href="css/styles.css">
```

## CSS

### Changing the Background Color:
To change the background color of an element, you use the `background-color` property.

#### Example:
```css
div {
    background-color: blue;
}
```
This will change the background color of all `<div>` elements to blue.

### Changing the Text Color
To change the color of text using CSS, you use the `color` property.

#### Example:
```css
p {
    color: red;
}
```
This will change the color of all text within `<p>` (paragraph) elements to red.

### Combining Both
If you want to set both the text color and background color for an element:

```css
section {
    color: white;
    background-color: green;
}
```
This will change the color of all text within `<section>` elements to white and the background color to green.

### Using Different Color Values:
You're not limited to just basic color names. CSS supports various methods to specify colors:

1. **Color Names:** There are about 140 named colors, e.g., `red`, `blue`, `goldenrod`, etc.
2. **Hexadecimal:** A six-digit code that represents color. E.g., `#FF0000` is red.
3. **RGB:** Stands for Red Green Blue. E.g., `rgb(255, 0, 0)` is red.
4. **RGBA:** Just like RGB but with an added Alpha (transparency) value. E.g., `rgba(255, 0, 0, 0.5)` is a semi-transparent red.
5. **HSL:** Stands for Hue Saturation Lightness. E.g., `hsl(0, 100%, 50%)` is red.