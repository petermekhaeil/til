# Cypress cy.clock()

[cy.clock()](https://docs.cypress.io/api/commands/clock) allows you to control time in your Cypress test:

```js
cy.clock();
cy.intercept('GET', '/pokemon').as('pokemon');
// 1st call
cy.wait('@pokemon');

// forward 10 seconds and wait for next `/pokemon` request
cy.tick(10_000);
cy.wait('@pokemon');
```

