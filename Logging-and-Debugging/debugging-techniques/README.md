## Text

Debugging is a crucial skill for developers. Various approaches and tools are available to help identify and resolve issues in the code we wrote.

- **Console Logging**:
  We can use `console.log()` statements to output specific values, messages, or variables to the browser console. While this may be simple and easy to implement, it provides limited visibility into the state of the application at a specific moment. Also it may clutter the codebase if not removed after debugging.

- **Breakpoints**:
  We can set breakpoints in the code using the browser's developer tools. The execution pauses at these breakpoints, allowing inspection of variables and the call stack. This provides a more interactive and dynamic debugging experience. It also allows step-by-step execution to understand the flow of the program.

- **Debugger Statements**:
  We can insert `debugger;` statements directly into the code. When the code is executed, it pauses at the debugger; line, allowing for inspection. This is quick and easy to implement. It offers a breakpoint-like experience without relying on the developer tools. But it needs to be removed after debugging, else can be intrusive if left in the production code.

- **Browser Developer Tools**:
  These are comprehensive suite of tools provided by browsers for inspecting and debugging web applications. It includes the Elements panel, Console, Sources, Network, etc. It allows real-time inspection of the DOM, CSS, and JavaScript. But it have an initial learning curve.

### Debugging a React application

[React debugging guide](https://raygun.com/blog/react-debugging-guide/)
[How to debug a react applicaation](https://dev.to/colocodes/how-to-debug-a-react-app-51l4)
[Debug using react dev tools](https://blog.logrocket.com/debug-react-apps-react-devtools/)
