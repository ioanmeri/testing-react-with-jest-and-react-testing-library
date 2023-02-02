# Introduction

## React Testing Library

- Not just a library, also a philosophy ("opinionated")
  - Test your software **the way users actually** use it
  - not internal implementation
  - Find elements by accessibility markers, not test IDs

**React Testing Library vs Jest**

- React Testing Library

  - Provides a virtual DOM for tests

- Jest
  - Test runner that
    - Finds tests
    - Runs tests
    - Determines whether tests pass or fail

---

## create-react-app

- npm package
- Creates React applications with...
  - Configuration
  - Webpack and Babel
  - Web server
  - Testing Library!

**npx**

- We will be using npx with create-react-app
  - Downloads the latest version of create-react-app templates every time
  - Not dependent on when you last installed create-react-app
  - Never installed on your machine!
- npx comes with npm 5.2+ and higher
- if you have an older version of npm and can't upgrade:
- Go to `https://github.com/facebook/create-react-app`
- Follow link "instructions for older npm versions"

---

## First Test with Testing Library

```
test('renders learn react link', () => {
  render(<App />);
  const linkElement = screen.getByText(/learn react/i);
  expect(linkElement).toBeInTheDocument();
})
```

**render**

- Create virtual DOM for argument JSX (<App />)
- Can access virtual DOM via screen global

**expect**

- assertion, causes test to succeed or fail

---

## Assertions

```
expect(linkElement).toBeInTheDocument();
```

**expect**

- Jest global, starts the assertion

**expect argument**

- subject of the assertion

**matcher**

- type of assertion
- this matcher comes from Jest-DOM

**Assertion examples**

```
expect(element.textContent).toBe('hello');
```

```
expect(elementsArray).toHaveLength(7);
```

**jest-dom**

- comes with create-react-app
- `src/setupTests.js` imports it before each test, makes matchers available
- DOM-based matchers
  - examples: `toBeVisible()` or `toBeChecked()`

---

## Jest

- React Testing Library helps with
  - rendering components into virtual DOM
  - searching virtual DOM
  - Interacting with virtual DOM
- Needs a test runner
  - Find tests, run them, make assertions
- Jest

  - is recommended by Testing Library
  - comes with create-react-app

- `npm test` runs an npm script that runs Just in watch mode

**Jest Watch Mode**

- Watch for changes in files since last commit
- Only run tests related to these files
- No changes? No tests
  - Type a to run all tests

**How does Jest Work?**

- global test method has two arguments:
  - string description
  - test function
- Test fails if error is thrown when running function
  - assertions throw errors when expectation fails
- No error => tests pass
  - Empty tests passes!

---

## TDD (Test-Driven Development)

- Write tests before writing code
  - then write code according to "spec" set by tests
- "red-green" testing
  - Tests fails before code is written

1. Write "shell" function

2. Write tests

3. Tests fail

4. Write code

5. Tests pass!

**Why TDD?**

- Makes a huge difference in how it feels to write tests
  - part of the coding process, not a "chore" to do at the end
- More efficient
  - Re-run tests "for free" after changes

---

## What does React Testing Library Do?

- Creates virtual DOM for testing
  - and utilities for interacting with DOM
- Allows testing without a browser

**Types of Tests**

- Unit tests
  - Tests one unit of code in isolation
- Integration tests
  - How multiple units work together
- Functional Tests
  - Tests a particular function of software
  - talking about behavior not particular code function
  - **testing behavior not code**
- Acceptance / End-to-end (E2E) Tests
  - Use actual browser and server (Cypress, Selenium)

---

## Functional Testing vs Unit Testing

**Unit Testing**

- Isolated: mock dependencies, test internals
- Advantage: Very easy to pinpoint failures
- Downside: Further from how users interact with software
- Downside: More likely to break with refactoring

**Functional Testing**

- different mindset from unit testing
- include all relevant units, test behavior
- Advantage: Close to how users interact with software
- Advantage: Robust tests
- More difficult to debug failing tests

---

## TDD (Test Driven Development) vs BDD (Behavior Driven Development)

- Quick detour for BDD: Behavior-Driven Development
- Testing Library encourage **testing behavior over implementation**
- So shouldn't we be calling this BDD instead of TDD?
  - actually, no.
- BDD is very explicitly defined
  - involves collaboration between lots of roles
    - developers, QA, business partners, etc
  - defines process for different groups to interact
- In this course, only developers, so TDD!

---

## Testing Library and Accessibility

**Accessibility and Finding Elements**

- Testing Library recommends finding elements by accessibility handles
  - [https://testing-library.com/docs/queries/about/#priority]

1. **Queries Accessible to Everyone**

- getByRole (button, heading)
- getByLabelText (forms)
- getByPlaceholderText (input)
- getByText (non interactive elements)
- getByDisplayValue (forms)

2. **Semantic Queries**

- getByAltText (images)
- getByTitle

3. **Test IDs**

- getByTestId

- Roles documentation: [https://www.w3.org/TR/wai-aria/#role_definitions]

- Can't find an element like a screen reader would?
  - Then your app isn't friendly to screen readers

---
