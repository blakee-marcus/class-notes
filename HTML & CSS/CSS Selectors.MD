#CSS Selectors

CSS selectors are patterns used to target and style HTML elements. They tell the browser which elements on the webpage should be styled and how to apply those styles. Here’s a breakdown of the main types of CSS selectors:

## 1. Element Selector

This targets all instances of a particular HTML element.

Example:

```css
p {
  color: blue;
}
```
This will make all `<p>` elements (paragraphs) on the page blue.

## 2. Class Selector

This targets elements that have a specific class attribute. Class selectors are prefixed with a dot (.).

Example:

```css
.highlight {
  background-color: yellow;
}
```
Any element with the class highlight will have a yellow background.

## 3. ID Selector

This targets a single element with a specific ID. The ID selector is prefixed with a hash (#). Since IDs are unique, it should only be used for one element on the page.

Example:

```css
#main-title {
  font-size: 24px;
}
```
The element with the ID `main-title` will have a font size of 24px.

## 4. Attribute Selector

This targets elements based on their attributes.

Example:

```css
input[type="text"] {
  border: 1px solid gray;
}
```
This will style all `<input>` elements where the type is set to "text".

## 5. Pseudo-classes

Pseudo-classes target elements in a specific state, like when a link is hovered over or a form input is focused.

Example:

```css
a:hover {
  text-decoration: underline;
}
```

This will underline links when they are hovered over.

## 6. Pseudo-elements

Pseudo-elements target specific parts of an element, such as the first line of text or content inserted before an element.

Example:

```css
p::first-line {
  font-weight: bold;
}
```
The first line of every paragraph will be bold.

## 7. Descendant Selector

This targets elements that are nested within a specific parent element.

Example:

```css
div p {
  color: green;
}
```
This will make all paragraphs inside a `<div>` green.

## 8. Child Selector

This targets direct children of a specific parent element.

Example:

```css
ul > li {
list-style-type: square;
}
```
This will apply a square bullet point only to the direct children `<li>` items of a `<ul>`.
