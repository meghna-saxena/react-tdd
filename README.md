# react-tdd

## Enzyme
- Enzyme is a tool that creates virtual DOM for testing
- Allows testing without browser

We need to see how components are rendered and how they respond to user input
CRA uses ReactDOM for this purpose
Enzyme uses ReactDOM under the hood

But enzyme interface give much more extensive toolkit to work with virtual DOM
Eg: 
- With enzyme we can search thru DOM using jQuery style selectors 
- Simulate simple events on DOM. Click on the node in virtual DOM or blur an element


### Shallow rendering
- Enzyme has this concept of shallow rendering
- Renders components only one level deep
So if you have parent component having several child components, it will render parent component but use 
placeholders for child components
- That lets us cleaner and quicker testing. 

Enzyme provides access to component `props` and `state`
  - Manipulate values, and check them in testing.


## Starting installation in CRA
- yarn add ajv to prevent error due to difference in dev dependencies
If you don't update jest, and you install the latest enzyme, you might get version incompatibilities between the jest installed with create-react-app and the latest enzyme.

- yarn add --save-dev jest enzyme jest-enzyme enzyme-adapter-react-16.3


___________________________________________________

Inside App.test.js

- Remove this line => import ReactDOM from 'react-dom';

- configure enzyme to use the particular enzyme-adapter


## Using enzyme in a test
- Use enzyme in jest framework
- Use `shallow` function from enzyme export
- `shallow` function takes JSX (e.g <App />), and returns `shallow wrapper`

```const wrapper = shallow(<App />)```

- shallow actaully renders the app, tests will pass of no error is thrown.

- Refer enzyme docs
    - Shallow rendering API
      - .debug() => String
      returns the DOM as a string
      `console.log(wrapper.debug());`


- Jest `expect`
- In mocha, chai is used as assertion library
- Refer Jest docs, `expect API`
- It has lot of assertions, and its job is to throw error when assertion is false, so that test fails.

Most commonly used assertion:
- .toBe(value)
- .toBeTruthy()
- .expect.stringContaining/Matching() and so forth


## Types of tests
