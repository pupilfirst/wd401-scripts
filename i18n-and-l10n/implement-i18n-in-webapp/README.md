## Script

In this lesson we will learn how to implement i18n in a web application.

We will add this feature in WD301 react codebase. Internationalizing a Vite + React application involves several steps to ensure that your application can be easily adapted to different languages and regions.

### Key steps

1. Select the library - You'll typically need a library for managing translations and a way to switch between languages. A popular choice for React applications is `react-i18next`
2. Set Up Configuration - Create a configuration file to initialize and configure the i18n library. This file can include options for setting default language, loading resources, and enabling features like language detection.
3. Create translation files - Create JSON or other resource files for each supported language with translation key-value pairs. Place these files in a folder structure that matches the language codes you plan to support.
4. Initialise and use translations in React components - use the utility functions provided by the library to translate strings in the component.

See you in the next lesson.

### References

- [Steps to add i18n in your web application](https://medium.com/coursera-engineering/6-steps-to-i18n-success-for-your-web-app-b5702a221860)
- [Use i18next in react application](https://medium.com/@pedr0d1as/how-to-use-i18n-in-your-react-app-1f26deb2a3d8)
- [react-i18next crash course](https://www.youtube.com/watch?v=SA_9i4TtxLQ)
