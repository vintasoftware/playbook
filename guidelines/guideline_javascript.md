
<!-- Things to consider:

VALIDATE: Maybe we should make a lib eslint-config-vinta?
VALIDATE: Should we always use const (except for async and generators) or function?
VALIDATE: Where do we stand on using Hooks, Context Providers, Lazy/Suspense?
VALIDATE: Cleaner code with async/await instead of promises?
VALIDATE: Should we add react-testing-library?
-->

## 1. Linting and Formatting

We use [React](https://reactjs.org/) as the primary library for frontend development. We believe that our JavaScript projects should always be well written and organized - so we care a lot about readability, following patterns, and good practices. In order to guarantee that a project is up to our standards, we configure `linters` and `code formatters` into it.

### 1.1 Use our ESLint shareable configurations

## 2. Project Structure

We follow a very simple and clean project structure and try to keep concerns separated while keeping our folder structures as flat as possible. See the example below:

```
+ apps
  + app-name
    + components
      + ComponentName
        - AuxiliarLocalComponent.js
        - ComponentName.js
        - Container.js
        - index.js
    + services
      + service-name
```

## 3. React Components

### 3.1 JSX Splitting

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

### 3.2 Conditional Rendering

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

- Avoid writing checks that can evaluate to `0`, as React will render it. Try to evaluate them to `false`, `undefined`, `null` or `''` instead. For instance, the example below can render either a list of items or `0`, since `itemList.length` returns a number:

  ```javascript
  // Bad
  const Component = ({ itemList }) => (
    itemList.length ? (
      <div>
        {itemList.map(item => (
          <div>{item.name}</div>
        ))}
      </div>
    ) : 'Nothing Found.'
  )

  // Good
  const Component = ({ itemList }) => (
    itemList.length > 0 ? (
      <div>
        {itemList.map(item => (
          <div>{item.name}</div>
        ))}
      </div>
    ) : 'Nothing Found.'
  )
  ```

### 3.3 Lifecycle methods

- Follow the ESLint rule [react/sort-comp](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/sort-comp.md) from `eslint-plugin-react` to organize your class components. The default order is:
  1. static methods and properties
  2. lifecycle methods: `displayName`, `propTypes`, `contextTypes`, `childContextTypes`, `mixins`, `statics`, `defaultProps`, `constructor`, `getDefaultProps`, `state`, `getInitialState`, `getChildContext`, `getDerivedStateFromProps`, `componentWillMount`, `UNSAFE_componentWillMount`, `componentDidMount`, `componentWillReceiveProps`, `UNSAFE_componentWillReceiveProps`, `shouldComponentUpdate`, `componentWillUpdate`, `UNSAFE_componentWillUpdate`, `getSnapshotBeforeUpdate`, `componentDidUpdate`, `componentDidCatch`, `componentWillUnmount` (in this order)
  3. Custom methods
  4. `render` method
- Avoid using `UNSAFE` methods, even in React 15. Unless there is no other way to implement something without them, and only if you're not using React 16+.

### 3.4 Composition

### 3.5 Styling

- Use [Styled Components](https://www.styled-components.com/) instead of pure `CSS`, `CSS Modules` or `SASS`.
- Keep the styling structure simple by using your styled components in the same file they were created.
- If there's need to export or extend an existing styled component, treat it as a normal component and only export one per file.
<!-- TODO: Add topics about styled-systems or xstyled? -->

### 3.6 Props & PropTypes

- Follow the ESLint rules [react/prop-types](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/prop-types.md), [react/no-unused-prop-types](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/no-unused-prop-types.md), and [react/forbid-prop-types](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/forbid-prop-types.md).
  - `react/prop-types` checks if every prop that is being used in the component is being defined in its `propTypes` object.
    - This rule can be configured to ignore certain prop names. To do so, check its [documentation](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/prop-types.md).
  - `react/no-unused-prop-types` checks if there are any prop types set in the component's `propTypes` object that are not being used inside its code.
  - `react/forbid-prop-types` forbids the use of the following types:
    1. `PropTypes.any` - Use the actual expected type instead. Not to be confused with `PropTypes.anyOf`, as this one should be allowed.
    2. `PropTypes.object` - use `PropTypes.shape` instead, and define the prop-type for each key inside that object (repeat for nested objects).
    3. `PropTypes.array` - use `PropTypes.arrayOf` instead, and define the types that are accepted by the array.

<!-- TODO: Discuss if this is worth mentioning -->
- Separate a group of props that is known to be repeated in several parts of the code, then import it instead of rewriting the types again:
  <!-- TODO: Discuss where to fit this in the project structure -->
  ```javascript
  const ComponentPropTypes = PropTypes.shape({
    name: PropTypes.string,
    value: PropTypes.string,
    quantity: PropTypes.number,
    categories: PropTypes.arrayOf(PropTypes.string)
  })

  Component.propTypes = {
    items: PropTypes.arrayOf(ComponentPropTypes)
  }

  export { ComponentPropTypes }
  export default Component
  ```

### 3.7 State Management

### 3.8 Imports

An import expression is formed by one or more `specifier` from a single `source`:

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
- When using React, keep the `React` and `PropTypes` imports always on top. Here's an example of how these rules can be applied:

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
  import LoginForm from 'apps/login/components/LoginForm';
  import { RANDOM_KEY, TYPES } from 'constants';
  import { withDebounce } from 'helpers/debounce';

  // Parent
  import App from '../app';

  // Sibling
  import Page from './page';
  ```

### 3.9 Exports

### 3.10 Portals
<!-- Only valid for React 16+ - Use react-portal to work with React 15 -->

### 3.11 Fragments

- Use [Fragments](https://reactjs.org/docs/fragments.html) instead of creating extra **unnecessary** elements to render a component that returns more than one element at the same level.

```javascript
// Bad
return (
  <div>
    <div>Element 1</div>
    <div>Element 2</div>
  </div>
)

// Good
return (
  <>
    <div>Element 1</div>
    <div>Element 2</div>
  </>
)
```

- Prefer using the fragments shorthand `</>` instead of `<React.Fragment />`, unless it receives props:

```javascript
// Bad
return (
  <React.Fragment>
    <div>Element 1</div>
    <div>Element 2</div>
  </React.Fragment>
)

// Good
return (
  <React.Fragment key={item.id}>
    <div>Element 1</div>
    <div>Element 2</div>
  </React.Fragment>
)

// Also good
return (
  <>
    <div>Element 1</div>
    <div>Element 2</div>
  </>
)
```

## 4. Redux

### 4.1 Selectors

### 4.2 Connecting Components

### 4.3 Actions

#### 4.3.1 Async Actions

### 4.4 Reducers

### 5. Forms

## 6. Tests

### 6.1 Jest

### 6.2 Enzyme
