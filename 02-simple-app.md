## Unit Testing Functions

**Functions separate from components**

- Used by several components
- Complex logic

**Unit test if**

- Complex logic difficult to test via functional tests
- Too many edge cases

---

## When to Unit Test

- `replaceCamelWithSpaces` is pretty simple
- could be covered by functional tests on button

Form more complicated functions, unit tests help with:

- covering all possible edge cases
- determining what causes functional tests to fail

**Issue with functional tests**

- high-level makes them resistant to refactors
- high-level makes them difficult to diagnose

---

## Review: Simple App

- Test interactivity **fireEvent**
- jest-dom assertions
  - toBeEnabled()
  - toBeDisabled()
  - toBeChecked()
- getByRole option { name: }
- Jest describe to group tests
- Unit testing functions

---
