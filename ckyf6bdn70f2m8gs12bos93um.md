## Cypress: Integration Tests Made Easy!

> Tdlr; I had put automated integration testing on the back burner due to "lack of time" but once I saw how easy it was - I felt rather silly for taking so long. Try out Cypress! You might be as surprised as I was!

I am not sponsored in any way in this post - this is purely my experience!

You can find Cypress at  [https://www.cypress.io/](https://www.cypress.io/) 

# How easy is it?
```js
it('Should see a button on first visit', () => {
  cy.get('.button').contains('cool popup button');
});

it('Should click button and view new feature', () => {
  cy.get('.button').contains('cool popup button').click();
  cy.get('div.popupClassName');
  cy.get('p').contains('New Feature Title');
});

it('Should click to view the details of the feature release', () => {
  cy.get('div.popupClassName > button').contains('more').click();
  cy.get('p').contains('Detailed View');
});
```

And that's it. Super easy.

# Mocking API calls
It is a good idea to have full end-to-end testing, but sometimes you want to purely test the front end of a project and mock all the api calls. 

```js
cy.intercept('GET', '**/endpointName*', {
  body: {
    data1: 123123,
    date2: 'content',
  },
});

cy.intercept('GET', '**/endpointName2*', {
  fixture: 'endpoints/endpointName2.json',
});
```

That is it. Seriously. 

# Conclusion
Sometimes it is worth taking 5 minutes to see how much effort a process is. I learned this after putting it off for far too long. Don't make the same mistake as me and start **today** on making integration testing part of your regular development workflow!

You can find Cypress at  [https://www.cypress.io/](https://www.cypress.io/) 