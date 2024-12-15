# HTML Elements

At the heart of HTML are its elements. These are the building blocks of any web page.

## Anatomy of an HTML Element:

```html
<tagname> Content goes here... </tagname>
```

### Opening Tag: 
This is the starting point of the element. It consists of the element's name (like `p`, `h1`, `div`) enclosed in opening and closing angle brackets.

### Content: 
This is the material placed between the opening and closing tags. It could be text, other HTML elements, or even nothing at all!

### Closing Tag: 
This concludes the element. It's very similar to the opening tag but has a forward slash (`/`) before the element's name.

### Examples:

#### Paragraph: 
```html
<p>This is a paragraph.</p>
```
#### Heading: 
```html
<h1>This is a main heading.</h1>
```

### Attributes:

Often, elements have additional information called "attributes". They provide extra details about the nature of the element. Attributes come in name/value pairs like: `name="value"`.

For example:
```html
<a href="https://www.example.com">Visit our website!</a>
```

In this case, `href` is an attribute name with the value "https://www.example.com", which indicates the link's destination.

### Some Common HTML Elements:

1. `<p>` - Defines a paragraph.
2. `<h1>, <h2>, ... <h6>` - Define headings. (`<h1>` is the highest/most important level).
3. `<a>` - Defines a hyperlink.
4. `<img>` - Used to embed images. Requires the src attribute to indicate the image source.
5. `<ul>` - Creates an unordered list, with `<li>` denoting each list item.
6. `<ol>` - Creates an ordered list.
7. `<div>` - A generic container, often used to group elements for styling or scripting.