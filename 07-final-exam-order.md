# Final Exam

## Debugging Tips

- `screen.debug()`: what the DOM looks like at that point

- `import { logRoles } from "testing-library/dom";

```
test("button has correct initial color", () => {
  const {container} = render(<App />);
  logRoles(container);
})
```

- Does getBy\* fail when a server call or other async action?
  - need to use await findBy\*
- userEvent **method without await**? (e.g.user.click)()
- Read test error output carefully
  - don't get intimidated by huge walls of text!
  - exactly which assertion is failing?
  - copy/paste error into web search
- Try pre-written code to see whether your tests or code are the issue
- Clearly not a viable option in real life, but useful tool while learning

---

## Resolving Error from Tests

- Unable to find `role="role"`

  - Either role (for example, button) doesn't exist, or no element with that role that also matches name option.

- Warning: An update to component inside a test was not wrapped in act(...)

  - There was an update to the component after the rest completed. Use useEffect cleanup and unmount()

- Waring: Can't perform a React state update on an unmounted component. This is a no-op, but it indicates a memory leak in your application.

  - There was an update to the component state after the test completed. Use **useEffect** cleanup and **unmount()**

- Error: connect ECONNREFUSED 127.0.0.1
  - There is no Mock Service Worker handler associated with this route and method.

---
