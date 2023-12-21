## Text

To complete this level, you are required to implement internationalization (i18n) and localization (l10n) features in a React.js application. The goal is to make the application accessible and user-friendly for a global audience by enabling the dynamic translation of content, localizing date and time formats, and providing the ability to switch between different locales.

- Dynamic Content Translation:

  - Implement a system for translating dynamic content within the React.js application. This involves creating language files or dictionaries that store translations for different languages.
  - Integrate a mechanism to dynamically switch between languages based on user preferences or system settings.
    Apply translation to various components, text elements, and messages throughout the application to ensure a seamless multilingual user experience.

- Date and Time Localization:

  - Localize date and time formats to accommodate different cultural preferences. Consider the variations in date formats (e.g., MM/DD/YYYY or DD/MM/YYYY) and time formats (12-hour vs. 24-hour clock).
  - Utilize libraries or functions that handle date and time localization, ensuring that timestamps are presented in a format consistent with the user's locale.

- Locale Switching:

  - Implement a user interface (UI) component or a settings panel that allows users to select their preferred language/locale.
  - Enable the application to respond dynamically to locale changes, updating content and formatting according to the selected locale.
  - Ensure that the locale switch is persistent across sessions, providing a smooth and personalized experience for users who want to interact with the application in their preferred language.

### Submission Guidelines

Prepare a document outlining the steps that is required to:

- set up a collaborative translation tool.
- How you added translation for each languages.
- How you set up your react project to make use of i18n.
- How you set up automatic language detector and switch the locale according to it.

## Script

In this level, you have learnt how to make your react app work with different languages.
I will be using the react project from WD301 to demo the features.

> Action: open https://www.npmjs.com/package/react-i18next in browser

We use the packages `i18next` and `react-i18n-next` to help us with the internationalisation or i18n.
I have also installed `i18next-browser-languagedetector` to help with automatic language detection.

> Action: Switch to `localhost:8080` in browser to show `traduora` dashboard.

I have used `traduora` to create translations for this project.

> Action: Switch to VSCode and show the locale files under `src/locales` folder.

I have both English and Spanish translations here.
I have exported the translations and have added it to our projects under `src/locales` folder.

> Action: Switch to localhost:5173 in browser and show the WD301 react project.

I have added the functionality to switch the locale when I toggle this switch.
It will toggle between english and spanish translations.
I have updated most of the components to make use of the translation rather than hard coded text.

> Action: Reload the page

It will persist even if I reload the page. The language detection package will pick it up and set the locale accordingly.

> Switch to VSCode and show how to use translation in a component.

So, I have a file called `i18n.ts`, in which I have all the initialisation of i18n package. It has the language detector, translations to be used, the fallback language etc. I have imported it in `App.tsx`.

Once set up, we can use the `useTranslation` hook to translate any key available in the translation files.

> Action: Open `projects/index.tsx` component.

For eg. In this `Projects` component, we use the `t` function to translate the key `Projects`. It will look up for the key in `en.json` and replace the key with corresponding value.

> Action: Switch to `tasks/NewTask.tsx` component.

Here, in `NewTask` component, we have similar usage for submit button and cancel button text.

This is how you add translation support in your application.
