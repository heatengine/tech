# React JS

## Installation
- Create new App
```npx create-react-app *application_name*```

## JSX
- embedding expression
```<h1>Hello {userName}!</h1>```

- Element as Object
```
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);

// OR

const element = {
  type: 'h1',
  props: {
    className: 'greeting',
    children: 'Hello, world!'
  }
};
```

## Rendering
- Does not update once rendered need to call render() again to update
```
ReactDOM.render(element, document.getElementById('root'));
```

## Component and Props
```
// Component as a Class
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}

// Component as a Function
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

// Rendering the component
const element = <Welcome name="Sara" />;
ReactDOM.render(
  element,
  document.getElementById('root')
);

// State is similar to props, but it is private and fully controlled by the component.
```

## State
- State is similar to props, but it is private and fully controlled by the component.
- It is local
```
// to set the state
this.setState({comment: 'Hello'});

// using callback
this.setState((state, props) => {
  // use or set state or props
});

```

## Event Handling
```
// react events are camelCase
// passing arguments
<button onClick={(e) => this.deleteRow(id, e)}>Delete Row</button>
<button onClick={this.deleteRow.bind(this, id)}>Delete Row</button>
```

## Conditional Rendering
- Using if else in functions
- Using logical ```&&``` operators
- Using (condition ? true : false)

## Rendering multiple elements using looping
```
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  // keys are used by React to identify elements in array
  // Keys Must Only Be Unique Among Siblings
  <li key="{number.toString()}">{number}</li>
);
ReactDOM.render(
  <ul>{listItems}</ul>,
  document.getElementById('root')
);
```