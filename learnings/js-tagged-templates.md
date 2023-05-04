# JavaScript: Tagged Template Literals

Tag templates (or tag functions) parse template literals with a function:

```js
function log(strings, ...args) {
  console.log(strings, args[0])
}

const person = "Peter";
log`My name is ${person}`;
// ['My name is ', ''] 'Peter'
```

First parameter is an array of strings, the following parameters are the variables that were passed in the expression. Think of them as substitutes. The string parts of the template have an index that matches the associated substitute that followed.

In the above example, `['My name is ', '']` was the string, `Peter` was the first substitute.

Tag templates can come useful in formatting strings:

```js
function introduce(strings, ...args) {
let formattedString = '';

  strings.forEach((string, i) => {
    formattedString += string + (args[i] ? args[i].toUpperCase() : '');
  });

 return formattedString;
}

var person = "Peter";
introduce`My name is ${person}`
// 'My name is PETER'
```

## Tagged Templates in the wild

- [Styled Components](https://styled-components.com/)

```js
const Button = styled.a`
  background: white;
  color: black;
`
```

- [graphql-tag](https://github.com/apollographql/graphql-tag)

```js
const query = gql`
  {
    user(id: 5) {
      firstName
      lastName
    }
  }
`
```

- [postgres](https://github.com/porsager/postgres)

```js
const users = await sql`
  select
    name,
    age
  from users
`
```

- [twin.macro](https://github.com/ben-rogerson/twin.macro)

```js
const Input = tw.input`border hover:border-black`
```
