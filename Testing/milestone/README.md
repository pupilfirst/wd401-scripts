## Text

In this lesson, we will make use of all the concepts that we learnt in this level and add those to our existing Node.js project.

On completing this level, you will have:

- Unit tests configured using Jest
- Integration tests configured using Cypress
- Have configured GitHub actions to run automatically when a new code is pushed.

### GitHub Action file

[Sample GitHub Action file](./main.yml)

### Screenshots

You should have something similar in GitHub actions:

![Github Action steps](./github-action.png)

There should be unit tests:

![Unit tests](./unit-test.png)

And integration tests as well.
![Integration tests](./integration-test.png)

## Script

In this lesson, we will apply the concepts that we have learnt in this level to an existing Node.js project.

I will be using the project from WD201 to demonstrate it.

> Action: Open WD201 Node.js project in VS Code.

So, If I switch to the project in VS Code. You can see I have some unit tests written in `__tests__` folder.

> Action: Switch to `package.json`.

In package.json, I have a command to run the tests using `jest`.

I can verify if the tests work by running it locally.

> Action: Run the command `npm test` and show test results.

Now, I also have some integration tests written using `Cypress`. I can run it locally and verify it also works.

To run the integration test, I need to have the app already up and running. So let's run the app first. Probably you will have to wipe off the database first. So that it always test against a clean database.

> Action: use command to drop, create and run migrations

```sh
npm run clean:start
```

Now, we can run the integration tests against this application. Open a new terminal, and run the following command.

> Action: Open new terminal and run `npm run cy:test  -- --env STUDENT_SUBMISSION_URL="http://localhost:3000/"`

The integration tests also looks good! Now, we can make use of GitHub actions to run these tests automatically whenever new commit is pushed.

> Action. Show `.github/workflows/main.yml` in VS Code.

Since, we need a postgres database, I have made use of containers in our workflow file. Make sure you have the correct database credentials as in `config/config.json`

Now, let's do a siple change and try pushing the changes.

> Action: Remove a comment or some minor change in a file, do commit and push. The open browser and visit to the repository and switch to `Actions` tab.

Now we can see the action is being executed. Let's wait. It will take few minutes to run the GitHub actions.

> Action: Switch to `main.yml` file and highlight different jobs in the file.

So we have following steps in the workflow.

1. We checkout the repository code
2. Then we will install dependencies
3. Then run the unit tests using the `npm test` command
4. Then we will run the app so that we can run integration tests
5. Finally run the integration test

We can also add some steps to do some output actions like triggering notification to Slack or Discord.

> Action: Switch back to browser and show the progress of tests.

Now you can see all our steps have passed and both unit and integrations tests are working as intended.

See you in the next level.
