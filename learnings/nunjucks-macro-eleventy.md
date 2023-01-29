# Using Nunjucks Macros in Eleventy

Nunjucks macros allows you to define reusable UI components that can be imported in your Eleventy pages when using the Nunjucks templating language:

```
{%- macro button(params) -%}
  <button type="{{ params.type }}">{{ params.text }}</button>
{%- endmacro -%}
```

Importing the macro in your page by referencing the filename and the macro name:

```
{%- from "button.macro.njk" import button -%}

{{ button({ type: "button", text: "Click Me" }) }}
```
