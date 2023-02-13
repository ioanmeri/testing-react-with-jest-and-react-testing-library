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
