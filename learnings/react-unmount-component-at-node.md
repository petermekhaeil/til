# Remove React app from the DOM

Use [ReactDOM.unmountComponentAtNode()](https://beta.reactjs.org/reference/react-dom/unmountComponentAtNode#unmountcomponentatnode) (React < 18) or [root.unmount()](https://beta.reactjs.org/reference/react-dom/client/createRoot#root-unmount) to remove a React app from the DOM.

```js
import ReactDOM from 'react-dom';

const domNode = document.getElementById('root');
ReactDOM.render(<App />, domNode);

ReactDOM.unmountComponentAtNode(domNode);
```

```js
import { createRoot } from 'react-dom/client';

const domNode = document.getElementById('root');
const root = createRoot(domNode);

root.render(<App />);

root.unmount();
```
