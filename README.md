# 🦏 React Rhino 

[![NPM Version](https://img.shields.io/npm/v/react-rhino)](https://www.npmjs.com/package/react-rhino)
![ESLint Check](https://github.com/aromalanil/react-rhino/workflows/ESLint-Check/badge.svg)
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/aromalanil/react-rhino/blob/master/LICENSE)
[![npm bundle size](https://img.shields.io/bundlephobia/minzip/use-custom-hooks)](https://www.npmjs.com/package/use-custom-hooks)

[![https://nodei.co/npm/react-rhino.png?downloads=true&downloadRank=true&stars=true](https://nodei.co/npm/react-rhino.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/react-rhino)

React Rhino is a simple yet powerful state management library for [React](https://reactjs.org/)

## Installation 

```bash
# If you use npm:
npm install react-rhino

# Or if you use Yarn:
yarn add react-rhino
```

## Usage

### Step 1
1. Create a `states.js` file in your `src` folder
2. Import `createRhinoState` from `react-rhino`

```js
import createRhinoState from 'react-rhino'
```

3. Pass an object to the `createRhinoState` function where the keys uniquely identify the state and values will be the initial value of the corresponding state.

```js
const { RhinoProvider, useRhinoState } = createRhinoState({
    name: "John Doe",
    isLoggedIn: true
})
```
4. `export` the `RhinoProvider` and `useRhinoState` from the file

```js
export { RhinoProvider, useRhinoState }
```

### Step 2
1. Import the `RhinoProvider` from the file and wrap the `App` component with it.

```js
import { RhinoProvider } from './states.js`
import App from "./App";

const rootElement = document.getElementById("root");
ReactDOM.render(
  <RhinoProvider>
    <App />
  </RhinoProvider>,
  rootElement
);

```

### Step 3
1. Import `useRhinoState` from the `states.js` to whichever component you want to use your global state.
```js
import { useRhinoState } from './states.js`
```
2. `useRhinoState` shares similar syntax with `useState` function. The only difference is that you pass a key to the hook instead of the initial value.
```js
const [name,setName] = useRhinoState("name")
```

> Note: Here "name" is the key identifying the state in the object we passed to `createRhinoState` function.


## Author
[Aromal Anil](https://aromalanil.tech)