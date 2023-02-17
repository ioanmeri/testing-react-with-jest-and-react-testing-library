# Simulating Server Response with Mock Service Worker

## Tests

- Test that option images render

- Mock Service Worker

- Mock server response for `/scoops` and `/toppings`

---

## Mock Service Worker

- Purpose:
  - intercept network calls
  - return specified responses
- Prevents network calls during tests
- Set up test conditions using server response

1. install

```
npm install msw
```

2. Create handlers

3 . Create test server

4. Make sure test server listens during all tests

- reset after each test

---

## Mock Service Worker Handler

```
rest.get('http://localhost:3030/scoops', (req, res, ctx) => {})
```

**Handler Type**: rest or graphql

- HTTP method to mock: get, post, etc.
- Full URL to mock
  - Response resolver function
    - req: request object
    - res: function to create response
    - ctx: utility to build response
      https://mswjs.io/docs/basics/response-resolver

---

## Mock Service Worker in Tests

**Options Component** -> **GET / scoops** -> Server

Mock service worker is going to intercept the request and send back the handler response to the options component.

---

## await findBy

When you are waiting for something to appear asynchronously on the page, you must use **await findBy**

**Review**

- Mock Service Worker mimics response from server
  - create handler
  - create server
  - update **setupTests** to listen for requests

---

## Only and skip tests

I can use `test.only` and `test.skip` to run only or skip specific tests.

---

## Review

- Override Mock Service Worker response for individual tests

- Misleading Unable to find role="alert" error

- Isolate file by typing p in Jest watch mode

- Isolate test within file with test.only or test.skip

- waitFor for tests where await findBy\* isn't enough

---
