# Sundaes on demand

- Choose ice cream flavors and toppings and submit order
- Flavors and toppings come from server
- order is sent to server

---

## Backdrop to Test...

- more complex user interactions
  - multiple **form entry**, moving through order phases
- mouseover popup
  - test that element disappears from DOM
- simulating server response
  - mock service worker
- async app updates
  - awaiting DOM changes
- global state via context

**Spoiler Alert**

- We will not be testing context implementation
  - only interested in testing behavior as seen by user!
- Tests no different if we used Redux, Mobx, etc
- Only difference in the test setup
  - make sure component is wrapped in context
  - ensure functionality
  - avoid errors

**Order Phase State (App-level)**

- inProgress
- review
- completed

---

## Set up ESLint and Prettier

- `npm install eslint-plugin-testing-library eslint-plugin-jest-dom`
- Remove **eslintConfig** from `package.json`
- Create `.eslintrc.json` and add standard config
- Add `.eslintcache` and `.vscode` to `.gitignore`
- Create `.vscode/settings.json` and add standard config
- Test that it worked in `App.test.js`:

```
expect(linkElement).toHaveAttribute('checked');
```

```
import {useEffect} from 'react';
```

---

## Styling

- course will use react-bootstrap
  - you can use any styling you want, or none
- `npm install react-bootstrap bootstrap`

---

## Code Organization

- Organize components by pages

  - **test** directory for each page
  - Jest will find and run any files that end in `.test.js`

- `src/pages/summary`
  - `OrderSummary.jsx`
  - `SummaryForm.jsx`
- `src/pages/summary/test`
  - `SummaryForm.test.jsx`

---

## User event

A way to simulate actual user events than just DOM events (the difference with fireEvent)

**Systax**

```
test("test case", async () = {
  const user = userEvent.setup();

  await user.click(checkbox);
})
```

---

## screen Query Methods

```
command[All]ByQueryType
```

**command**

- get: expect element to be in DOM
- query: expect element not to be in DOM
- find: expect element to appear async

**[All]**

- (exclude) expect only on match
- (include) expect more than one match

**QueryType**

- Role (most preferred)
- AltText (images)
- Text (display elements)
- Form elements

  - PlaceholderText
  - LabelText
  - DisplayValue

- https://testing-library.com/docs/dom-testing-library/api-queries
- https://testing-library.com/docs/react-testing-library/cheatsheet/
- https://testing-library.com/docs/guide-which-query

---

## SummaryForm Review

- (review) testing flow where checkbox controls whether button is disabled
- mouseover for terms and conditions: userEvent
  - Requires setup step: `user = userEvent.setup();`
  - All methods are promises and **must** be awaited
  - methods `user.hover` and `user.unhover`
- for elements starting out **not** on page
  - `queryByText`
  - `expect().not.toBeInTheDocument()`

---
