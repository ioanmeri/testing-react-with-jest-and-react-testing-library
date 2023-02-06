# ESLint and Prettier

## ESLint

**Linter**: analyzes static text and marks syntax that breaks rules

**Static**: analyze code as written, not what happens when code is run

- Popular linter for JavaScript
- Linting keeps code style consistent
  - especially for multi-eng projects
- Also catches errors in code
  - using variable before defining
  - importing from nonexisting file
  - etc

**Linting vs. Formatting**

- Formatters (like prettier) automatically format code (indents, spacing)
  - example: spaces around curly braces

from:

```
import {useEffect} from 'react';
```

to:

```
import { useEffect } from 'react';
```

- **Linters** address **format** and **style**
  - example: preferred assertion method

from:

```
expect(checkbox).toHaveAttribute(checked);
```

to:

```
expect(checkbox).toBeChecked();
```

### ESLint Plugins

- Plug-ins extend ESLint
- Testing Library and jest-dom ESLint plugins
  - Enforce best practices

https://github.com/testing-library/eslint-plugin-testing-library

https://github.com/testing-library/eslint-plugin-jest-dom

---

## ESLint for Testing Library and Jest DOM

```
npm install eslint-plugin-testing-library eslint-plugin-jest-dom
```

- Create root dir `.vscode` and add:

```
{
  "editor.codeActionsOnSave": {
    "source.fixAll": true
  },
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true
}
```

---

## Review: Setting up ESLint and Prettier

- ESLint:

  - `npm install eslint-plugin-testing-library eslint-plugin-jest-dom`
  - **Remove** eslintConfig **from package.json**
  - Create `.eslintrc.json` and add standard config
  - Install ESLint extension for VSCode
  - Create `.vscode/settings.json` and add standard config
  - Add `.eslintcache` and `.vscode` to `.gitignore`

- Prettier:
  - Add settings to `.vscode/settings.json`
  - Install Prettier on VSCode

---
