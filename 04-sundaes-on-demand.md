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
