# HOC Pattern

This pattern is an advanced pattern and alternatively called as Decorator Pattern. It is used for reusing component logic across our application. For example:

- Components that use Third Party Subscription Data.
- Enhance Various Card Views with the same design elements, such as shadow and border.
- App Components that require logged in user data.
- Situation needing infinite scrolling in three different views, all with different data.

A high-order component is nothing but JavaScript higher-order function, they are pure functions with no side effects.

HOC is a JavaScript function that takes a component as an argument and returns another component after injecting or adding additional data and functionality to the returned component. These components fundamental concept is based upon React's nature, which prefers composition over inheritance.

## Example:
```javascript
import React, { Component } from "react";

const higherOrderComponent = (DecoratedComponent) => {
    class HOC extends Component {
        render() {
            return <DecoratedComponent />
        }
    }

    return HOC;
};
```

## Popular React HOC Integrations to know:
- **react-router:** withRouter(UserPage)
- **react-redux:** connect(mapStateToProps, mapDispatchToProps)(UserPage)
- **material-ui:** withStyles(styles)(UserPage)