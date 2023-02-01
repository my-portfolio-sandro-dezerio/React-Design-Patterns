# Compound Component Pattern

This pattern helps establish seamless communication between a parent and children's components via a flexible and expressive API. Using this pattern, the parent component can interact and share state with the children components implicity. It provides an effective method for various components to share states and handle logic. Compound components are best suitable for React apps where you need to build declarative UI.

## Example:

```javascript
const Option = ({ children, onClick, active }) => {
    return (
        <div
            style={
                active ? { background: "grey" } : { background: "white" }
            }
            onClick={onClick}
        >
            <p>{chidlren}</p>
        </div>
    );
};

const Select = ({ options }) => {
    const [selectedOption, setSelectedOption] = useState(null);

    return options.map(({ key, value }) => (
        <Option
            active={selectedOption === key}
            onClick={() => setSelectedOption(value)}
        >
            {key}
        </Option>
    ))
}

const App = () => (
    <Select
        options={[
            { key: "Oliver", value: "oliver" },
            { key: "Eve", value: "eve" }
        ]}
    />
);
```

## When use Compound Components ?
- The child components are required to be inside the scope of a parent component, and they need to share behaviour and state.
- You need to render a user interface based on static data that is provided beforehand.