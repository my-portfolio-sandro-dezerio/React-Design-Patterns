# Conditional Rendering Pattern

There are many instances where developers need to render elements based on certain conditions for creating React screens. A practical example of this pattern will be if we need to integrate an authentication option in our app. For instance, if we are providing an authentication option, we need to make a 'log out' button that remains visible when the user is logged in to the app and a Login/SignUp button for when the user is signed out or is visiting the app for the first time.

## Example using if:
This type of conditional rendering is used when we want to render some element only when one specific condition is passed.

```javascript
const users = [
    { id: "1", firstName: "Robin", lastName: "Wieruch" },
    { id: "2", firstName: "Dennis", lastName: "Wieruch" }
];

function App() {
    return (
        <div>
            <h1>Hello Conditional Rendering</h1>
            <List list={users}>
        </div>
    );
}

function List({ list }) {
    if (!list) {
        return null;
    }

    return (
        <ul>
            {list.map((item) => (
                <Item key={item.id} item={item} />
            ))}
        </ul>
    );
}

function Item({ item }) {
    return (
        <li>
            {item.firstName} {item.lastName}
        </li>
    );
}
```

## Example using if/else:
Using if/else is one of the most popular conditional rendering methods. It's ideal for situations where developers ened to execute more than a single line of code inside if or else block or outside the scope of JSX.

```javascript
if (userProfile.role === "superadmin") {
    initSuperAdminFunction();
    initSuperAdminComponent();
    // other block of codes...
} else if (userProfile.role === "admin") {
    initAdminFunction();
    initAdminComponent();
    // other block of codes...
} else {
    initUserComponent();
    // other block of codes...
}
```

## Example using ternary operator:

>Example assigning variable value.
```javascript
// Conditional rendering with common if else
let isDrinkTea;
if (role === "developer") {
    isDrinkTea = true;
} else {
    isDrinkTea = false;
}

// Conditional rendering with ternary operator
let isDrinkTea = role === "developer" ? true : false;
```

>Example with a function for return value.
```javascript
// Conditional rendering with common if else
function isDrinkTea(role) {
    if (role === "developer") {
        return true;
    } else {
        return false;
    }
}

// Conditional rendering with ternary operator
function isDrinkTea(role) {
    return role === "developer" ? true : false;
}
```

## Example using && operator:
There is a simpler alternative to using the ternary operator. You can make use of a short-circuit AND operator for replacing a ternary operator like:

```javascript
// Instead of using the ternary operator...
{
    isShow ? <SmallComponent /> : null
}

// We can use short-circuit && operator...
{
    isShow && <SmallComponent />
}
```

For the ternary operator, when there is no value assigned to the 'else' condition, you need to write the ': null' expression to avoid an error. When using short-circuit && operator, we don't need to write a null expression.

## Example using Switch Case:
Another conditional operator often used as an alternative to if/else statements. However, the use case for this is a little different.

For instance, if you are working on a blogging app and you need to display different layouts for different user roles:

```javascript
function App(props) {
    const { role } = props;
    switch (role) {
        case "author":
            return <AuthorLayout> Let's write something </AuthorLayout>;
        case "admin":
            return <AdminLayout> Here are the latest reports </AdminLayout>;
        case "moderator":
            return <ModeratorLayout> These are the ongoing events </ModeratorLayout>;
        default:
            return <GuestLayout> Your current feed </GuestLayout>;
    }
}
```