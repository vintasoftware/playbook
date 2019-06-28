
<!-- Things to consider:

VALIDATE: Maybe we should make a lib eslint-config-vinta?
VALIDATE: Should we always use const (except for async and generators) or function?
VALIDATE: Where do we stand on using Hooks, Context Providers, Lazy/Suspense?
VALIDATE: Cleaner code with async/await instead of promises?
VALIDATE: Should we add react-testing-library?
-->

## 1. Linting and Formatting

We use [React](https://reactjs.org/) as the primary library for frontend development. We believe that our JavaScript projects should always be well written and organized - so we care a lot about readability, following patterns, and good practices. In order to guarantee that a project is up to our standards, we configure `linters` and `code formatters` into it.

### 1.1 Use ESLint with Prettier

- Prettier will focus on fixing your code's formatting. Here's how we configure it in our projects:

    ```json
    // .prettierrc.json
    {
      "printWidth": 100,
      "useTabs": false,
      "tabWidth": 2,
      "semi": true,
      "singleQuote": true,
      "trailingComma": "es5",
      "jsxBracketSameLine": true,
      "arrowParens": "avoid",
      "bracketSpacing": true
    }
    ```

- Follow prettier's [recommended configuration](https://prettier.io/docs/en/integrating-with-linters.html#recommended-configuration) to work with ESlint. This enables ESLint to accept Prettier's rules when linting.
- ESLint will focus on rules that won't meddle with Prettier's standards.
- Configure ESLint to extend `eslint-config-airbnb`, but also use prettier's React rules:

    ```json
    {
      "extends": [
          "airbnb",
          "plugin:prettier/recommended",
          "prettier/react"
        ],
        ...
    }
    ```

- Install the following plugins:
  - [eslint-plugin-promise](https://github.com/xjamundx/eslint-plugin-promise)
  - [eslint-plugin-jest](https://github.com/jest-community/eslint-plugin-jest)
  - [eslint-plugin-sonarjs](https://github.com/SonarSource/eslint-plugin-sonarjs)

## 2. Project Structure

## 3. JavaScript Basics

## 4. React Components

### 4.1 JSX Splitting

- Try to split big components into smaller more readable ones whenever deemed necessary.
- Avoid splitting JSX into variables or methods inside another component:

  ```javascript
  // Bad
  const Login = () => {
    const form = (
      <form>
        <input type="text" name="username" />
        <input type="text" name="password" />
        <button type="submit">Login</button>
      <form>
    )

    return (
      <div>
        <div>Login</div>
        {form}
      </div>
    )
  }

  // Also bad
  class Login extends React.Component {
    renderForm() {
      return (
        <form>
          <input type="text" name="username" />
          <input type="text" name="password" />
          <button type="submit">Login</button>
        <form>
      )
    }

    render() {
      return (
        <div>
          <div>Login</div>
          {this.renderForm()}
        </div>
      )
    }
  }
  ```

- If splitting the JSX code is really necessary, split it into a new component:

  ```javascript
  // Good
  const LoginForm = () => (
    <form>
      <input type="text" name="username" />
      <input type="text" name="password" />
      <button type="submit">Login</button>
    <form>
  )

  const Login = () => (
    <div>
      <div>Login</div>
      <LoginForm />
    </div>
  )
  ```

**Why?** So consistency and readability for JSX can be mantained. When writing a component, the only places where JSX should be present are: *after a return, for functional components*, and *inside the render method (also after a return) for class components*.

### 4.2 Conditional Rendering

- Use ternaries (`?:`), `if/else` or `switch/case` to handle conditional rendering cases.
- Avoid writing complex condition checks inside the JSX. Separate them into new functions, methods, or variables instead.

  ```javascript
  // Bad
  const ConditionalComponent = ({ items }) => (
    <div>
      {items && items.filter((i) => i.type === 'TAG').length > 0 ? (
        <TagList items={items} />
      ) : (
        'Nothing found.'
      )}
    </div>
  )

  // Good
  const ConditionalComponent = ({ items }) => {
    const hasTags = items && items.filter((i) => i.type === 'TAG').length > 0
    return (
      <div>
        {hasTags ? (
          <TagList items={items} />
        ) : (
          'Nothing found.'
        )}
      </div>
    )
  }
  ```

- Avoid using big chunks of JSX code inside multiple conditions. Separate them into smaller components instead.
<!-- TODO: Add example -->

- Avoid writing checks that can evaluate to `0`, as React will render it. Try to evaluate them to `false`, `undefined`, `null` or `''` instead.
<!-- TODO: Add example -->

### 4.3 Lifecycle methods

- Follow the ESLint rule [react/sort-comp](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/sort-comp.md) from `eslint-plugin-react` to organize your class components. The default order is:
  1. static methods and properties
  2. lifecycle methods: `displayName`, `propTypes`, `contextTypes`, `childContextTypes`, `mixins`, `statics`, `defaultProps`, `constructor`, `getDefaultProps`, `state`, `getInitialState`, `getChildContext`, `getDerivedStateFromProps`, `componentWillMount`, `UNSAFE_componentWillMount`, `componentDidMount`, `componentWillReceiveProps`, `UNSAFE_componentWillReceiveProps`, `shouldComponentUpdate`, `componentWillUpdate`, `UNSAFE_componentWillUpdate`, `getSnapshotBeforeUpdate`, `componentDidUpdate`, `componentDidCatch`, `componentWillUnmount` (in this order)
  3. Custom methods
  4. `render` method
- Avoid using `UNSAFE` methods, even in React 15. Unless there is no other way to implement something without them, and only if you're not using React 16+.

### 4.4 Composition

### 4.5 Styling

### 4.6 Props & PropTypes

- Follow the ESLint rules [react/prop-types](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/prop-types.md), [react/no-unused-prop-types](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/no-unused-prop-types.md), and [react/forbid-prop-types](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/forbid-prop-types.md).
  - `react/prop-types` checks if every prop that is being used in the component is being defined in its `propTypes` object.
    - This rule can be configured to ignore certain prop names. To do so, check its [documentation](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/prop-types.md).
  - `react/no-unused-prop-types` checks if there are any prop types set in the component's `propTypes` object that are not being used inside the its code.
  - `react/forbid-prop-types` forbids the use of the following types:
    1. `PropTypes.any` - Use the actual expected type instead. Not to be confused with `PropTypes.anyOf`, as this one should be allowed.
    2. `PropTypes.object` - use `PropTypes.shape` instead, and define the prop-type for each key inside that object (repeat for nested objects).
    3. `PropTypes.array` - use `PropTypes.arrayOf` instead, and define the types that are accepted by the array.

<!-- TODO: Discuss if this is worth mentioning -->
- Separate a group of props that is known to be repeated in several parts of the code, then import it instead of rewriting the types again:
  <!-- TODO: Discuss where to fit this in the project structure -->
  ```javascript
  const ComponentItem = PropTypes.shape({
    name: PropTypes.string,
    value: PropTypes.string,
    quantity: PropTypes.number,
    categories: PropTypes.arrayOf(PropTypes.string)
  })

  Component.propTypes = {
    items: PropTypes.arrayOf(ComponentItem)
  }

  export { ComponentItem }
  export default Component
  ```

### 4.7 State Management

### 4.8 Imports

A import expression is formed by one or more `specifier` from a single `source`:

```javascript
import DefaultSpecifier, { Specifier1, Specifier2 } from 'source'
import * as NamespaceSpecifier from 'source'
```

A file's import section can be a mess if you're not careful. It's important to keep the `sources` and `specifiers` well grouped and sorted. So we follow a few rules to keep things organized:

- Group imports by `source` type:
  - **Builtin**: The source is a builtin node module.
  - **External**: The source is an external installed library.
  - **Internal**: The source is a folder in your local project.
  - **Parent**: The source is an internal file from one or more directories above the file that is importing it.
  - **Sibling**: The source is an internal file in the same directory of the one that is importing it.
- Sort sources in each group alphabetically.
- Sort specifiers alphabetically.
- While using React, keep the `React` and `PropTypes` imports always on top. Here's an example of how these rules can be applied:

  ```javascript
  // main React imports
  import React from 'react';
  import PropTypes from 'prop-types';

  // Builtin
  import fs from 'fs';
  import path from 'path';

  // External
  import { connect } from 'react-redux';
  import { bindActionCreators } from 'redux';

  // Internal
  import { withDebounce } from 'app/components/debounce';
  import LoginForm from 'app/components/login';
  import { RANDOM_KEY, TYPES } from 'app/constants';

  // Parent
  import App from '../app';

  // Sibling
  import Page from './page';
  ```

### 4.9 Exports

### 4.10 Portals
<!-- Only valid for React 16+ - Use react-portal to work with React 15 -->

### 4.11 Fragments
<!-- Only valid for React 16+ -->

## 5. Redux

### 5.1 Selectors

### 5.2 Connecting Components

### 5.3 Actions

#### 5.3.1 Async Actions

### 5.4 Reducers

### 6. Forms

## 7. Tests

### 7.1 Jest

### 7.2 Enzyme
