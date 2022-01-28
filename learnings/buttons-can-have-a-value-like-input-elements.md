# Buttons can have a value like input elements

The `<button>` element can have a value like `<input>` and this value can also be passed to the server when the form is submitted:

```html
<form action="#" method="POST">
  <input type="text" name="name" value="Peter" />
  <button type="submit" name="_action" value="add">Add</button>
  <button type="submit" name="_action" value="delete">Delete</button>
</form>
```

The form can be submitted with this data without the need of JavaScript. On the server, you can check the value of `_action` to decide what to do next based on which button the user clicked to submit the form.


If you are submitting the form programmatically using JavaScript, `FormData` needs to know which button was used to submit the form:  

```js
document.querySelector("form").addEventListener("submit", (event) => {
  event.preventDefault();

  const formData = new FormData(event.target);

  // The FormData does not know how the form was submitted. 
  // There could be more than one submit button on the form and
  // we want to include the one that was used to submit the form. 
  // We append the button (also known as the submitter) to FormData.
  // See more: https://developer.mozilla.org/en-US/docs/Web/API/SubmitEvent/submitter
  if (event.submitter) {
    formData.append(event.submitter.name, event.submitter.value);
  }

  const data = Object.fromEntries(formData.entries());
  console.log(data); // {name: "Peter", _action: "add"}
  
  // When ready, submit the form programmatically
});
```

[Remix](https://remix.run/) does a great job at using this technique - they demonstrate it in their video [Remix Single: Multiple Forms and Single Button Mutations](https://www.youtube.com/watch?v=w2i-9cYxSdc). The Remix implementation can be found [here](https://github.com/remix-run/remix/blob/db2c31f64affb2095e4286b91306b96435967969/packages/remix-react/components.tsx#L856).

