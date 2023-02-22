# Testing Components Wrapped in a Provider

## Context File

- Kent C. Dodds pattern to set up context with embedded state

- https://kentcdodds.com/blog/application-state-management-with-react

- context file
  - make context with `createContext`
    - make custom hook with `useContext`
    - make context provider with internal state via `useState`
    - Provider value state getters and setters
- export custom hook and provider

---

## Review: Scoops Subtotal with Context

- getByText **to find total**
  - **exact option** set to false
- number inputs
  - **await** and **findBy** (coming from server async)
  - spinbutton role
  - **userEvent.clear** to clear existing text
  - **userEvent.type** to enter number
- wrapper option to render to apply context provider
- Redefine Testing Library render to access universally

--
