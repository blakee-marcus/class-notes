# Built-In Helpers #

Handlebars.js provides a number of built-in helpers that allow you to perform conditional rendering in your templates. These helpers allow you to include or exclude blocks of content based on certain conditions.

Here's an example of a template that uses the `if` helper to conditionally render a block of content:

```javascript
{{#if userLoggedIn}}
  <p>Welcome back, {{userName}}!</p>
{{else}}
  <p>Please log in to continue.</p>
{{/if}}
```

In this example, the block of content between the `{{#if}}` and `{{else}}` tags will be rendered if the `userLoggedIn` variable is `true`, and the block of content between the `{{else}}` and `{{/if}}` tags will be rendered if the userLoggedIn variable is false.

You can also use the `unless` helper, which works the same as the `if` helper but inverts the condition. For example:

```javascript
{{#unless userLoggedIn}}
  <p>Please log in to continue.</p>
{{/unless}}
```

This will render the block of content if the `userLoggedIn` variable is `false`.

You can also use the `compare` helper to perform more advanced comparisons. For example:

```javascript
{{#compare age '>=' 18}}
  <p>You are an adult.</p>
{{else}}
  <p>You are not yet an adult.</p>
{{/compare}}
```

In this example, the block of content between the `{{#compare}}` and `{{else}}` tags will be rendered if the `age` variable is greater than or equal to 18, and the block of content between the `{{else}}` and `{{/compare}}` tags will be rendered if the `age` variable is less than 18.

These are just a few examples of how you can use Handlebars.js helpers to perform conditional rendering in your templates. You can find more information about Handlebars.js helpers in the documentation: https://handlebarsjs.com/guide/builtin-helpers.html