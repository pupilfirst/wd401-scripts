## Text

This milestone requires integration of error tracking and debugging features into a React.js application to enhance the application's stability, identify and resolve issues efficiently. The key features to implement are:

- Error Tracking System:

  - Integrate a robust error tracking system that captures and logs errors occurring within the React.js application. Consider using third-party tools or libraries that specialize in error tracking, such as Sentry or Rollbar.
  - Ensure that the error tracking system collects relevant information about the errors, including stack traces, error messages, and contextual data such as user actions leading to the error.
  - Configure alerts or notifications to inform developers promptly when critical errors occur, allowing for quick response and resolution.

- Debugger Capability:

  - Implement debugging capabilities to facilitate the identification and resolution of issues during development and testing.
  - Leverage tools like React DevTools or other browser developer tools to inspect component hierarchies, examine state and props, and debug application logic.
  - Enable breakpoints, stepping through code, and inspecting variable values to streamline the debugging process and empower developers to isolate and fix issues efficiently.

### Submission Guidelines

Write in detail the steps taken to:

- add an error tracking system in your react project.
- how you used debugger to track a bug in your application.
- write an RCA for the above found bug.

## Script

In this level, you have learnt how to add an error tracking system and monitor your application for bugs.

> Action: Display sentry page and the react project configured.

I am using the react project from WD301. I have followed the instructions and set up sentry to receive any crashes that might happen.

> Action: Switch to VS Code and display the sentry sdk code to send any crash info.

I have added the sentry sdk and have initialised it in `Main.tsx`. If we have any crash, it will be updated in sentry.

> Action: Show the manual throw error code in `Appbar.tsx`

I have added code to throw an error when we toggle the locale.

> Action: Show error code in `DragDropList.tsx`

I have also added code to throw error when we move a task card from one list to another.

> Action: run `npm run build` command

Now, let's try taking a production build and run it.

```sh
npm run build
```

You can see, the source maps is uploaded to sentry. This helps sentry to figure out which file or line in source code threw error, since when taking a production build, the source gets minified.

Now, let's run it.

> Action: Run the command `npm run preview`

```sh
npm run preview
```

> Action: Open url `localhost:4173`

Let's open the url `localhost:4173`. I have opened the developer tools as well. We should see a crash when I toggle the locale.

> Action: Toggle the locale switch.

There is some network call happening to sentry. That should be the crash log.

> Action: Switch to senty dashboard.

We have the error populated in sentry dashboard. It is correctly displaying which file and line the crash occurred!

> Switch back to react application.

Now, let's try moving a task.

> Action: Try to move a task from one list to another.

We got another error!. It is also populated in sentry.

This is how we track errors and crashes in production.
