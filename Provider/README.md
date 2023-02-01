# Provider Pattern

React developers every day faces one of the major problem is Props drilling. Props drilling in which data is passed down to different children components until it gets to the component where the prop is needed.

This plot is not a problem, until it becomes a pain when the components which doesn't need  the props share the data.

This is where the Provide Pattern comes to help. The Provider pattern helps us to store/keep the data in a one location, e.g. React Context State/Object and the Redux store.

The Context Provider/Store can then send this data to any component that needs it directly without Props drilling.

For example: Take a theme logic like dark mode / light mode, to use this you need to pass the theme object to unrelated components to reach the particular component which uses the theme object. Because of this if any change happens to the theme object all the unrelated components will get triggered and re-renders which affects the performance of the app. To avoid this we can use is Provider Pattern.

## Example:

> React - Redux Provider Design Pattern Structure.
```javascript
import React from "react";
import ReactDOM from "react-dom";

import { Provider } from "react-redux";
import sotre from "./store";

import App from "./App";

const rootElement = document.getElementById("root");

ReactDOM.render(
    <Provider store={store}>
        <App />
    </Provider>,
    rootElement
);
```