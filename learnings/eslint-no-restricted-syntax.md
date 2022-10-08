#  ESLint's `no-restricted-syntax` rule
ESLint's `no-restricted-syntax` uses [selectors](https://eslint.org/docs/latest/developer-guide/selectors) to query an AST and this can be used to restrict certain syntax from being used.

Use a [AST Explorer](https://astexplorer.net/) to view the resulting AST of the JavaScript code you want to query.

This rule disallows the use of `MyLibrary.myFunction()`:

```json
{
  "rules": {
    "no-restricted-syntax": [
      "error",
      {
        "selector": "MemberExpression[property.name='myFunction'][object.name='MyLibrary']",
        "message": "'MyLibrary.myFunction()' is depreciated. Please use MyOtherLibrary.myNewFunction()"
      }
    ]
  }
}
```

This rule disallows the use of `MyLibrary().myFunction()`:

```json
{
  "rules": {
    "no-restricted-syntax": [
      "error",
      {
        "selector": "[property.name='myFunction'] CallExpression[callee.name='MyLibrary']",
        "message": "'MyLibrary().myFunction()' is depreciated. Please use MyOtherLibrary.myNewFunction()"
      }
    ]
  }
}
```
