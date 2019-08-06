# Frontend Tech Stack

## Recommended

### React

- **Routing**
  - [react-router](https://github.com/ReactTraining/react-router) - Declarative routing for React
  - [react-router-dom](https://github.com/ReactTraining/react-router/tree/master/packages/react-router-dom) - DOM bindings for React Router
- **Styling**
  - [styled-components](https://www.styled-components.com/) - Allows you to write actual CSS code to style your components. It also removes the mapping between components and styles
  - [@xstyled/styled-components](https://github.com/smooth-code/xstyled) - Consistent theme based CSS for styled-components
- **Forms**
  - [formik](https://jaredpalmer.com/formik/) - A small library that helps you with the 3 most annoying parts of form development: getting values in and out of form state, validation/error messages and handling form submission
  - [redux-form](https://redux-form.com/) - A Higher Order Component using react-redux to keep form state in a Redux store

### Redux

- **Async Actions / Side Effects**
  - [redux-thunk](https://github.com/reduxjs/redux-thunk) - A middleware for redux which lets you write async logic that interacts with the store
  - [redux-saga](https://github.com/redux-saga/redux-saga) - A library that aims to make application side effects easier to manage, more efficient to execute, easy to test, and better at handling failures
- **Caching**
  - [redux-persist](https://github.com/rt2zz/redux-persist) - Uses the localStorage to persist and rehydrate a redux store

### Requests

- [axios](https://github.com/axios/axios) - Promise based HTTP client for the browser and node.js
- [fetch (builtin)](https://developer.mozilla.org/en/docs/Web/API/Fetch_API) - Provides an interface for fetching resources (including across the network)

### Formatters

- [prettier](https://prettier.io/) - Autoformats the code using its own rules (limited configuration)

### Linters

- **ESLint**
  - [babel-eslint](https://github.com/babel/babel-eslint) - Helps eslint to identify and lint babel features correctly
  - [eslint-config-prettier](https://github.com/prettier/eslint-config-prettier) - Adds the prettier rules to eslint, raising errors when the code differs from prettier's expected output.
  - [eslint-config-airbnb](https://github.com/airbnb/javascript) - Adds Airbnb's config (already contains react, import and jsx-a11y configurations).
  - [eslint-plugin-prettier](https://github.com/prettier/eslint-plugin-prettier) - Turns off formatting-related rules that might conflic with prettier.
  - [eslint-plugin-jest](https://github.com/jest-community/eslint-plugin-jest) - Adds support to jest.
  - [eslint-plugin-promise](https://github.com/xjamundx/eslint-plugin-promise) - Adds rules for promise-related cases.
  - [eslint-plugin-sonarjs](https://github.com/SonarSource/eslint-plugin-sonarjs) - SonarJS rules for ESLint to detect bugs and suspicious patterns in your code

### Tests

- [jest](https://jestjs.io/) - Facebook's javascript test runner
- [babel-jest](https://github.com/babel/babel-jest) - Jest addon that adds support to babel features
- [jest-styled-components](https://github.com/styled-components/jest-styled-components) - A set of utilities for testing Styled Components with Jest.
- [enzyme](https://airbnb.io/enzyme/) - Airbnb's javascript testing utility for react that makes it easier to test your react components' output.
- [enzyme-adapter-react-\*](https://github.com/airbnb/enzyme/tree/master/packages/enzyme-adapter-react-16) - Adds support to enzyme for your current react version (replace \* with the version major number).
- [enzyme-to-json](https://github.com/adriantoine/enzyme-to-json) - Adds a serializer that converts enzyme wrappers to a format compatible with jest snapshot testing.
- [redux-mock-store](https://github.com/dmitry-zaets/redux-mock-store) - A mock wrapper for the redux store.
- [sinon](https://sinonjs.org/) - A testing lib with standalone test spies, stubs and mocks.


### Schema Validation

- [yup](https://github.com/jquense/yup) -

### Data Normalization

- [normalizr](https://github.com/paularmstrong/normalizr) -

### Utils

- [lodash](https://lodash.com/) -

### Dates

- [moment](https://momentjs.com/) -
- [moment-timezone](https://momentjs.com/timezone/) -

### Environment

- [dotenv](https://github.com/motdotla/dotenv) -

### Documentation

- [storybook](https://storybook.js.org/) -

### Webpack

- [html-webpack-plugin](https://github.com/jantimon/html-webpack-plugin) -

## Currently Testing

### React

- **Animations**
  - [react-pose](https://popmotion.io/pose/) -
- **Lists**
  - [react-sortable-hoc](https://github.com/clauderic/react-sortable-hoc) -

### Requests

- [ky](https://github.com/sindresorhus/ky) - A tiny and elegant HTTP client based on the browser Fetch API.

### Immutability

- [immutable-js](https://github.com/immutable-js/immutable-js) -
- [immer](https://github.com/immerjs/immer) -

## To Analyze

### React

- **Lists**
  - [react-virtuoso](https://github.com/petyosi/react-virtuoso) -
  - [react-virtualized](https://github.com/bvaughn/react-virtualized) -
- **Tables**
  - [react-data-grid](https://adazzle.github.io/react-data-grid/) -
  - [react-table](https://github.com/tannerlinsley/react-table) -
- **Tests**
  - [react-testing-library](https://github.com/testing-library/react-testing-library)
- **Form**
  - [react-form](https://github.com/tannerlinsley/react-form) -
  - [formsy-react](https://github.com/christianalfoni/formsy-react) -
  - [use-form-react](https://github.com/amazingandyyy/use-form-react) -
  - [react-reactive-form](https://github.com/bietkul/react-reactive-form) -
- **File Upload**
  - [uppy](https://uppy.io/) -
  - [react-filepond](https://github.com/pqina/react-filepond) -
- **Styling**
  - [styled-system](https://styled-system.com/) - Responsive, theme-based style props for building design systems with React

### Redux

- **Async Actions**
  - [debounce-action](https://github.com/jshanson7/debounce-action) -
- **Selectors**
  - [reselect](https://github.com/reduxjs/reselect) -

## Not Recommended

### Requests

- [got](https://github.com/sindresorhus/got) - *Got is a human-friendly and powerful HTTP request library.* Not recommended to use with frontend code, use [axios](https://github.com/axios/axios) or [ky](https://github.com/sindresorhus/ky) instead.
