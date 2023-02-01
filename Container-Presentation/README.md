# Container and Presentational Components Pattern

## Container Components
Container components are in charge of how things work. They are usually class components that contain required lifecycle methods and Presentational components. It is also where the data fetching happens and most of your logic is written.

### Example:
```javascript
class Users extends React.Component {
    state = {
        users: []
    }

    componentDidMount() {
        this.fetchUsers();
    }

    render() {
        return (
            // ... jsx code with presentation component.
        );
    }
}
```

## Presentational Components:
These are components that are in charge of how the UI looks. They don't have any possession with any part of the app and are just used to display data or you can call this as dumb components, because these components do not own any logic that are related to app or to rendering. Just display what you give to them.

### Example:
```javascript
const userList = ({users}) => {
    return (
        <ul>
            {users.map((user) => (
                <li key={user.id}>
                    {user.username}
                </li>
            ))}
        </ul>
    );
};
```