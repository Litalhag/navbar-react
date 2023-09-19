1. **useState**

   - **What is it?**
     Think of it as a way to keep track of a piece of data that can change over time.
   - **Analogy**:
     Imagine a scoreboard in a game. The score can change, and each time it does, the display updates.
   - **Example**:
     ```javascript
     const [score, setScore] = useState(0)
     // Now you can use 'score' to display it, and 'setScore' to update it.
     ```

2. **useEffect**

   - **What is it?**
     Lets you perform side-effects (like fetching data, updating the DOM, etc.) in function components.
   - **Analogy**:
     When you walk into a room and the light is too dim, you might decide to turn on more lights (reacting to the state of the room). useEffect lets you react to changes like that.
   - **Example**:
     ```javascript
     useEffect(() => {
       console.log('Score has changed to', score)
     }, [score])
     // This will log to the console every time 'score' changes.
     ```

- **Examples od useEffect:**

1. **Fetching Data**: Initiate API calls to fetch data from a server when a component mounts or when specific state/props change.

2. **DOM Manipulations**: Directly manipulate the DOM when the component renders or updates. This is rare in React (since the framework itself deals with the DOM), but it's required when integrating with non-React libraries.

3. **Subscriptions**: Set up and clean up subscriptions, like websockets or event listeners. For example, listening for keypress events or real-time data changes.

4. **Timers and Intervals**: Start (and clean up) timers, intervals, or request animation frames for animations or periodically fetching data.

5. **Side Effects with Cleanup**: Sometimes, side effects need cleanup to prevent memory leaks or other issues. An example is removing event listeners or clearing timers/intervals. The cleanup function can be returned from the effect to handle this.

6. **Updating Document Title or Meta**: Change the document title or metadata based on the component's state or props.

7. **Persisting State**: For example, saving state to `localStorage` when it changes so it can be restored later.

8. **Logging**: Log specific changes or events for debugging or analytics purposes.

9. **Focus Management**: For example, focusing on an input field under certain conditions.

10. **Interacting with External Libraries**: Integrate with third-party or non-React libraries, like D3 for data visualization or jQuery plugins.

11. **Preventing or Triggering Re-renders**: Sometimes you might want to manually control when a component re-renders, and `useEffect` combined with other hooks or logic can assist in that.

12. **Syncing State Between Components**: In cases where you're trying to coordinate state between two sibling components, you might use `useEffect` to respond to changes in context values or other external triggers.

13. **Updating State Based on Props**: While direct derivation of state from props is discouraged in many scenarios, there are times when you might want to update state in response to prop changes, and `useEffect` can help in those cases.

The core idea behind `useEffect` is to handle side effects — operations that can't be performed during the regular render flow of a React component. When thinking about when to use `useEffect`, consider if the operation you're thinking of falls into this category. If it does, `useEffect` is likely the tool you need.

---

3. **useRef**

   - **What is it?**
     Lets you access and interact with DOM elements directly. It can also hold a mutable value that doesn’t trigger a re-render when it changes.
   - **Analogy**:
     Think of it as a bookmark. In a big book (your webpage), you can place a bookmark on a specific page (an element) to easily return to it.
   - **Example**:
     ```javascript
     const inputRef = useRef(null)
     // Now you can use inputRef to directly access an input element.
     // <input ref={inputRef} />
     // To focus on this input: inputRef.current.focus();
     ```
