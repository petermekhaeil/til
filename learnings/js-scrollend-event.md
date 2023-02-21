# JavaScript: scrollend event

The new [scrollend](https://developer.mozilla.org/en-US/docs/Web/API/Document/scrollend_event) event fires when scrolling has ended. 

```js
addEventListener("scrollend", (event) => {});

onscrollend = (event) => {};
```

Previously before this event, there was no straightforward way to detect when scrolling has ended. We would have had to use the `onscroll` and a timer to detect if scrolling has ended. 

Read the full write-up on [developer.chrome.com](https://developer.chrome.com/blog/scrollend-a-new-javascript-event/).
