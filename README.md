
# 🌟 React Interview Questions 🌟

## 1. What is React? 🎯
**React** is a **JavaScript library** developed by Facebook for building **user interfaces**, especially for single-page applications. It enables creating dynamic and interactive UIs by efficiently handling data changes.

```jsx
const element = <h1 style={{ color: "blue" }}>Hello, world! 🌎</h1>;
```

---

## 2. Key Features of React 🔑
- **JSX**: Syntax extension for writing HTML-like code in JavaScript.
- **Components**: Reusable and independent UI blocks.
- **Virtual DOM**: Improves performance by updating only what's necessary.
- **One-way data binding**: Ensures data flows in a single direction.
- **React Hooks**: Add state and lifecycle methods to functional components.

---

## 3. What is JSX? 📝
JSX is a syntax extension for **JavaScript**, allowing you to write HTML-like syntax directly within JavaScript code.

```jsx
const element = <h1>Hello, world! 🌍</h1>;
```

---

## 4. What is a Component in React? 🔧
Components are the **building blocks** of a React application. They can be **class-based** or **functional**.

### 🏷 Class Component:
```jsx
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}
```

### 🏷 Functional Component:
```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}! 👋</h1>;
}
```

---

## 5. State vs. Props in React 🔄
- **State**: Local data specific to a component, which can change over time.
- **Props**: Inputs passed to components from their parent.

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}! 🎉</h1>; // 'name' is a prop.
}
```

---

## 6. What is the Virtual DOM? 🖥️
The **Virtual DOM** is a lightweight representation of the actual DOM. React updates the **Virtual DOM** first and compares it to the previous version before updating the actual DOM, improving performance.

---

## 7. How Does React Handle Events? 📅
React uses **camelCase** for event handlers, and you must prevent the default behavior manually.

```jsx
function handleClick() {
  alert('Button clicked! 🖱️');
}

<button onClick={handleClick}>Click me! 💥</button>;
```

---

## 8. What is the `useState` Hook? 🪝
The `useState` hook allows functional components to manage state.

```jsx
function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times!</p>
      <button onClick={() => setCount(count + 1)}>Click me! ➕</button>
    </div>
  );
}
```

---

## 9. What is the `useEffect` Hook? 🔄
The `useEffect` hook handles side effects, such as fetching data or updating the DOM.

```jsx
useEffect(() => {
  document.title = `Clicked ${count} times 📊`;
}, [count]); // Re-runs when `count` changes
```

---

## 10. Passing Data Between Components 📨
Pass data from a parent component to a child component using **props**.

```jsx
function Parent() {
  return <Child message="Hello from Parent! 👪" />;
}

function Child(props) {
  return <p>{props.message}</p>;
}
```

---

## 11. Higher-Order Components (HOCs) ⬆️
**HOCs** are functions that take a component and return a new one with enhanced functionality.

```jsx
function withLogger(WrappedComponent) {
  return function (props) {
    console.log('Logging... 📝');
    return <WrappedComponent {...props} />;
  };
}
```

---

## 12. What are React Hooks? 🎣
Hooks like `useState` and `useEffect` allow functional components to have state and side effects.

```jsx
const [name, setName] = useState('John Doe 🌟');
```

---

## 13. What is `useMemo`? 📈
The `useMemo` hook memoizes expensive calculations, optimizing performance.

```jsx
const memoizedValue = useMemo(() => calculateValue(a, b), [a, b]);
```

---

## 14. React Context 🗂️
**React Context** allows sharing global data, like themes or user information, without passing props manually at every level.

```jsx
const ThemeContext = React.createContext('light');

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Toolbar />
    </ThemeContext.Provider>
  );
}
```

---

## 15. How to Optimize Performance in React? 🚀
- **Memoization** with `React.memo`.
- **Code splitting** using `React.lazy` and `Suspense`.
- Use `useMemo` and `useCallback` for expensive functions.
- Optimize state and avoid unnecessary renders.

---

## 16. Controlled vs. Uncontrolled Components 🎛️
- **Controlled Components**: React controls the form data.
- **Uncontrolled Components**: DOM handles form data via refs.

```jsx
<input value={this.state.value} onChange={this.handleChange} /> // Controlled

<input ref={inputRef} /> // Uncontrolled
```

---

## 17. React Router 🚦
React Router provides routing between components for single-page applications.

```jsx
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';

<Router>
  <Switch>
    <Route path="/" exact component={Home} />
    <Route path="/about" component={About} />
  </Switch>
</Router>
```

---

## 18. Conditional Rendering 🎭
You can conditionally render components based on logic using JavaScript operators.

```jsx
{isLoggedIn ? <Dashboard /> : <Login />}
```

---

## 19. What is `useRef`? 🛠️
`useRef` stores values across renders or accesses DOM elements directly.

```jsx
const inputRef = useRef(null);
inputRef.current.focus(); // Focuses the input element.
```

---

## 20. `useEffect` vs. `useLayoutEffect` ⏳
- **`useEffect`**: Runs after the component is painted.
- **`useLayoutEffect`**: Runs synchronously before the paint, useful for DOM measurements or updates.



