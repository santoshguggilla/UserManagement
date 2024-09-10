# React Interview Question

---

### 1. **What is React?**
   - **Explanation**: React is a JavaScript library created by Facebook for building user interfaces, especially for single-page applications. It allows developers to build web applications that can update and render efficiently in response to data changes.
   - **Example**: A React application renders components that react to state changes.

### 2. **What are the key features of React?**
   - **Key Features**:
     1. **JSX**: A syntax that allows mixing HTML with JavaScript.
     2. **Components**: Reusable, independent pieces of UI.
     3. **Virtual DOM**: React uses a virtual representation of the real DOM for better performance.
     4. **One-way data binding**: Data flows in one direction, making the code easier to debug.
     5. **React Hooks**: Functional components that allow the use of state and side-effects.

### 3. **What is JSX?**
   - **Explanation**: JSX is a syntax extension for JavaScript that resembles HTML. It allows developers to write HTML-like code within JavaScript.
   - **Example**:
     ```jsx
     const element = <h1>Hello, world!</h1>;
     ```

### 4. **What is a component in React?**
   - **Explanation**: Components are the building blocks of any React app. A component can be a class component or a functional component.
   - **Example**:
     - **Class component**:
       ```jsx
       class Welcome extends React.Component {
         render() {
           return <h1>Hello, {this.props.name}</h1>;
         }
       }
       ```
     - **Functional component**:
       ```jsx
       function Welcome(props) {
         return <h1>Hello, {props.name}</h1>;
       }
       ```

### 5. **Explain the concept of state and props in React.**
   - **State**: Local data specific to a component, which can change over time.
   - **Props**: Short for properties, they are inputs passed to components from their parent.
   - **Example**:
     ```jsx
     function Welcome(props) {
       return <h1>Hello, {props.name}</h1>; // 'name' is a prop.
     }
     ```

### 6. **What is the Virtual DOM and how does it work?**
   - **Explanation**: The Virtual DOM is a lightweight copy of the actual DOM. When changes occur, React updates the Virtual DOM first, compares it to the previous version, and only updates the changed parts in the real DOM.
   - **Example**: When a component’s state changes, only the affected part of the DOM gets updated instead of re-rendering the entire DOM.

### 7. **How does React handle events?**
   - **Explanation**: React events are handled similarly to DOM events but with some differences, such as camelCase syntax and the need to prevent default behavior manually.
   - **Example**:
     ```jsx
     function handleClick() {
       alert('Button clicked!');
     }
     <button onClick={handleClick}>Click me</button>;
     ```

### 8. **What is the `useState` hook?**
   - **Explanation**: `useState` allows you to add state to functional components.
   - **Example**:
     ```jsx
     function Counter() {
       const [count, setCount] = useState(0);
       return (
         <div>
           <p>You clicked {count} times</p>
           <button onClick={() => setCount(count + 1)}>Click me</button>
         </div>
       );
     }
     ```

### 9. **What is the `useEffect` hook and why is it used?**
   - **Explanation**: `useEffect` performs side effects in functional components (e.g., data fetching, DOM manipulation). It can run after every render or conditionally.
   - **Example**:
     ```jsx
     useEffect(() => {
       document.title = `You clicked ${count} times`;
     }, [count]); // Only re-runs when `count` changes.
     ```

### 10. **How do you pass data between components?**
   - **Explanation**: Data can be passed down from a parent component to a child component using props.
   - **Example**:
     ```jsx
     function Parent() {
       return <Child message="Hello from Parent" />;
     }
     function Child(props) {
       return <p>{props.message}</p>;
     }
     ```

---

### 11. **What are Higher-Order Components (HOCs)?**
   - **Explanation**: A Higher-Order Component is a function that takes a component and returns a new component. It is used to share logic across multiple components.
   - **Example**:
     ```jsx
     function withLogger(WrappedComponent) {
       return function (props) {
         console.log('Logging...');
         return <WrappedComponent {...props} />;
       };
     }
     ```

### 12. **What are React Hooks?**
   - **Explanation**: Hooks are functions that let you use state and lifecycle features in functional components. Common hooks include `useState`, `useEffect`, `useContext`, `useMemo`, etc.
   - **Example**:
     ```jsx
     const [name, setName] = useState('John'); // Example of `useState`.
     ```

### 13. **What is `useMemo` and when would you use it?**
   - **Explanation**: `useMemo` memoizes a value to avoid recalculating it unnecessarily. It’s useful for optimizing performance in expensive computations.
   - **Example**:
     ```jsx
     const memoizedValue = useMemo(() => expensiveCalculation(a, b), [a, b]);
     ```

### 14. **What is React Context?**
   - **Explanation**: Context provides a way to share data (like theme or user data) globally across the component tree without having to pass props down manually at every level.
   - **Example**:
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

### 15. **How do you optimize the performance of a React application?**
   - **Explanation**: Techniques include:
     - **Memoization** (`React.memo`): To avoid unnecessary re-renders.
     - **Code splitting**: Using React.lazy and Suspense to load components only when needed.
     - **Use of `useMemo` and `useCallback`** to optimize expensive computations or functions.
     - **Avoiding large state objects**.

### 16. **What is the difference between controlled and uncontrolled components?**
   - **Explanation**: Controlled components are those where the form data is handled by React state, while uncontrolled components handle form data via the DOM.
   - **Example**:
     - **Controlled**: 
       ```jsx
       <input value={this.state.value} onChange={this.handleChange} />
       ```
     - **Uncontrolled**: 
       ```jsx
       <input ref={inputRef} />
       ```

### 17. **What is React Router and how do you implement routing in React?**
   - **Explanation**: React Router is used to manage navigation between different components in React. 
   - **Example**:
     ```jsx
     import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';

     <Router>
       <Switch>
         <Route path="/" exact component={Home} />
         <Route path="/about" component={About} />
       </Switch>
     </Router>
     ```

### 18. **How do you handle conditional rendering in React?**
   - **Explanation**: Use JavaScript’s conditional operators like `if`, ternary operators, or logical `&&`.
   - **Example**:
     ```jsx
     {isLoggedIn ? <Dashboard /> : <Login />}
     ```

### 19. **What is the `useRef` hook used for?**
   - **Explanation**: `useRef` allows you to persist values across renders or directly interact with DOM elements.
   - **Example**:
     ```jsx
     const inputRef = useRef(null);
     inputRef.current.focus();
     ```

### 20. **What is the difference between `useEffect` and `useLayoutEffect`?**
   - **Explanation**: `useEffect` runs after the render is painted on the screen, while `useLayoutEffect` runs synchronously before painting.
   - **Use Case**: `useLayoutEffect` is used for measuring or manipulating the DOM.

---
