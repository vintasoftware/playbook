We use [React](https://reactjs.org/) as the primary library for frontend development. We believe that our JavaScript projects should always be well written and tidy - so we care a lot about readability, attention to patterns, and good practices.

## 1. Linting and Formatting

In order to guarantee that a project is up to our standards, we use our own ESLint & Prettier configurations. They handle most readability and best practices cases for you. [Check them out here](https://github.com/vintasoftware/eslint-config-vinta).

*Since `eslint-config-vinta` guarantees that our good practices are being respected, this guideline brings a collection of practices that ESLint can't fix automatically.*

## 2. React Components

### 2.1 JSX Splitting

- Split big components into smaller more readable ones whenever deemed necessary.
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
    );

    return (
      <div>
        <div>Login</div>
        {form}
      </div>
    );
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
      );
    }

    render() {
      return (
        <div>
          <div>Login</div>
          {this.renderForm()}
        </div>
      );
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
  );

  const Login = () => (
    <div>
      <div>Login</div>
      <LoginForm />
    </div>
  );
  ```

- Consistency and readability for JSX should be mantained. When writing a component, the only places where JSX should be present are: *after a return, for functional components*, and *inside the render method (also after a return) for class components*.

### 2.2 Conditional Rendering

- Use ternaries (`?:`) or `if/else` to handle *multiple, but small,* conditional rendering cases.

```javascript
  // Good
  const ConditionalComponent = ({ items, isLoading }) => {
    const hasTags = items && items.filter((i) => i.type === 'TAG').length > 0;
    return (
      isLoading ? (
        <Loading />
      ) : hasTags ? (
        <TagList items={items} />
      ) : (
        'Nothing found.'
      )
    );
  }

  // Better
  const ConditionalComponent = ({ items, isLoading }) => {
    const hasTags = items && items.filter((i) => i.type === 'TAG').length > 0;

    if (isLoading) {
      return <Loading />;
    }

    if (!hasTags) {
      return 'Nothing found.';
    }

    return <TagList items={items} />;
  }
```

- Avoid writing complex condition checks inside the JSX. Separate them into new functions, methods, or variables instead.

  ```javascript
  // Bad
  const ConditionalComponent = ({ items }) => (
    items && items.filter((i) => i.type === 'TAG').length > 0 ? (
      <TagList items={items} />
    ) : (
      'Nothing found.'
    )
  );

  // Good
  const ConditionalComponent = ({ items }) => {
    const hasTags = items && items.filter((i) => i.type === 'TAG').length > 0;
    return (
      hasTags ? (
        <TagList items={items} />
      ) : (
        'Nothing found.'
      )
    );
  }

  // Better
  const ConditionalComponent = ({ items }) => {
    const hasTags = items && items.filter((i) => i.type === 'TAG').length > 0;
    if (!hasTags) {
      return 'Nothing found.';
    }

    return <TagList items={items} />;
  }
  ```

- Avoid using big chunks of JSX code within conditionals. Separate them into smaller components instead.

  ```javascript
  // Bad
  const Component = ({ isFormOpen, onClick }) => (
    <div>
      {isFormOpen ? (
        <form>
          {/* Big form structure here */}
        </form>
      ) : (
        <button onClick={onClick}>Open form</button>
      )}
    </div>
  );

  // Good
  const Component = ({ isFormOpen, onClick }) => (
    <div>
      {isFormOpen ? (
        <FormComponent />
      ) : (
        <button onClick={onClick}>Open form</button>
      )}
    </div>
  );

  const FormComponent = () => (
    <form>
      {/* Big form structure here */}
    </form>
  );
  ```

- Avoid writing checks that can evaluate to `0`, as React will render it. Try to replace them to `false`, `undefined`, `null` or `''` instead. For example, the component below can render either a list of items or `0`, since `itemList.length` returns a number:

  ```javascript
  // Bad
  const Component = ({ itemList }) => (
    <>
      itemList.length && (
        <div>
          {itemList.map(item => (
            <div>{item.name}</div>
          ))}
        </div>
      )
    </>
  );

  // Good
  const Component = ({ itemList }) => (
    <>
      itemList.length > 0 && (
        <div>
          {itemList.map(item => (
            <div>{item.name}</div>
          ))}
        </div>
      )
    </>
  );
  ```

### 2.3 Lifecycle methods

- Follow the ESLint rule [react/sort-comp](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/sort-comp.md) from `eslint-plugin-react` to organize your class components. The default order is:
  1. static methods and properties
  2. lifecycle methods: `displayName`, `propTypes`, `contextTypes`, `childContextTypes`, `mixins`, `statics`, `defaultProps`, `constructor`, `getDefaultProps`, `state`, `getInitialState`, `getChildContext`, `getDerivedStateFromProps`, `componentWillMount`, `UNSAFE_componentWillMount`, `componentDidMount`, `componentWillReceiveProps`, `UNSAFE_componentWillReceiveProps`, `shouldComponentUpdate`, `componentWillUpdate`, `UNSAFE_componentWillUpdate`, `getSnapshotBeforeUpdate`, `componentDidUpdate`, `componentDidCatch`, `componentWillUnmount` (in this order)
  3. Custom methods
  4. `render` method
- Avoid using `UNSAFE` methods, even in React 15. Unless there is no other way to implement something without them and only if you're not using React 16+.

### 2.4 Styling
<!-- TODO (Jota): Add examples for styled components: mobile first, themes, nested components -->
- Use [Styled Components](https://www.styled-components.com/) instead of pure `CSS`, `CSS Modules` or `SASS`.
- Keep the styling structure simple by using your styled components in the same file they were created.
- If there's need to export or extend an existing styled component, treat it as a normal component and only export one per file.

### 2.5 Props & PropTypes

- Follow the ESLint rules [react/prop-types](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/prop-types.md), and [react/no-unused-prop-types](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/no-unused-prop-types.md).
- `react/prop-types` checks if every prop being used in the component is defined under the `Component.propTypes` object. This rule can be configured to ignore certain prop names; to do so, check its [documentation](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/prop-types.md).
- `react/no-unused-prop-types` checks if there are any prop types set in the component's `propTypes` object that are not being used inside its code.

- Separate a group of props that are known to be repeated in several parts of the code, then import them instead of rewriting the types again:

  ```javascript
  const ComponentPropTypes = PropTypes.shape({
    name: PropTypes.string,
    value: PropTypes.string,
    quantity: PropTypes.number,
    categories: PropTypes.arrayOf(PropTypes.string),
  });

  Component.propTypes = {
    items: PropTypes.arrayOf(ComponentPropTypes),
  };

  export { ComponentPropTypes };
  export default Component;
  ```

- If the case above happens a lot, it's wise to create a `types.js` file to store the PropTypes.

- Use the prefix `render` when naming a [Render Prop](https://reactjs.org/docs/render-props.html)

### 2.6 Portals

- Use [Portals](https://reactjs.org/docs/portals.html) when working with components like modals and toasts (basically any component that needs to be always on top).
- The [react-portal](https://github.com/tajo/react-portal) lib makes it easier to work with portals (and also makes it possible to use portals with React 15). Creating a portal with this is as simple as writing:

  ```javascript
    import { Portal } from 'react-portal';

    const Modal = ({ children }) => (
      <Portal>
        {children}
      </Portal>
    );
  ```

### 2.7 Fragments

- Use [Fragments](https://reactjs.org/docs/fragments.html) instead of creating extra **unnecessary** elements to render a component that returns more than one element at the same level.

  ```javascript
  // Bad (unless the parent div is REALLY necessary)
  return (
    <div>
      <div>Element 1</div>
      <div>Element 2</div>
    </div>
  );

  // Good
  return (
    <>
      <div>Element 1</div>
      <div>Element 2</div>
    </>
  );
  ```

- Prefer using the fragments shorthand `</>` instead of `<React.Fragment />`, unless it receives props:

  ```javascript
  // Bad
  return (
    <React.Fragment>
      <div>Element 1</div>
      <div>Element 2</div>
    </React.Fragment>
  );

  // Good
  return (
    <React.Fragment key={item.id}>
      <div>Element 1</div>
      <div>Element 2</div>
    </React.Fragment>
  );

  // Also good
  return (
    <>
      <div>Element 1</div>
      <div>Element 2</div>
    </>
  );
  ```

- Avoid using fragments if there's no reason to:

  ```javascript
  // Bad
  return (
    <>
      <div>Element 1</div>
    </>
  );

  // Good
  return (
    <div>Element 1</div>
  );
  ```

## 3. Imports

An import expression is formed by one or more `specifier` from a single `source`:

```javascript
import DefaultSpecifier, { Specifier1, Specifier2 } from 'source';
import * as NamespaceSpecifier from 'source';
```

A file's import section can be quite the mess if you're not careful. It's important to keep  `sources` and `specifiers` well grouped and sorted. So we follow a few rules to keep things organized:

- Group imports by `source` type:
  - **Builtin**: The source is a builtin node module.
  - **External**: The source is an external installed library.
  - **Internal**: The source is a folder in your local project.
  - **Parent**: The source is an internal file from one or more directories above the file that is importing it.
  - **Sibling**: The source is an internal file in the same directory of the one that is importing it.
- Sort sources in each group alphabetically.
- Sort specifiers alphabetically.
- When using React, keep the `React` and `PropTypes` imports always on top of the external group. Here's an example of how these rules can be applied:

  ```javascript
  // Builtin
  import fs from 'fs';
  import path from 'path';

  // External (node_modules libs)
  import React from 'react';
  import PropTypes from 'prop-types';
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

  > See ESLint rule: [import/order](https://github.com/benmosher/eslint-plugin-import/blob/master/docs/rules/order.md). This rule will help with the imports sorting by section, but not alphabetically.

<!--
## PROJECT ARCHITECTURE?

## 4. Redux

### 4.1 Selectors

### 4.2 Connecting Components

### 4.3 Actions

#### 4.3.1 Async Actions

### 4.4 Reducers
-->
