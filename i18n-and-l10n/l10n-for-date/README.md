## Script

In this lesson, we will learn how to display the date, time and currency based on user locale.

Localising date, time, and currency formats is essential when creating applications or content for a global audience. Different countries and regions have their own conventions for how these formats should appear.

### Date localisation

Date localisation involves formatting dates according to the conventions of a specific locale. In most programming languages, you can use built-in libraries or third-party libraries to handle date formatting. In JavaScript, we can make use of `Intl.DateTimeFormat` to format date and time.

```js
const date = new Date();

// Create a date formatter for a specific locale
const dateFormatter = new Intl.DateTimeFormat("fr-FR", {
  year: "numeric",
  month: "long",
  day: "numeric",
});

// Format the date
const formattedDate = dateFormatter.format(date); // Example output: "27 septembre 2023"
```

In this example, 'fr-FR' represents the French locale, and the formatting options specify how the date should be presented.

### Time localisation

Localizing times involves formatting time values according to locale-specific conventions. You can use a similar approach as with date localisation, but this time focusing on time formatting.

```js
const date = new Date();

// Create a time formatter for a specific locale
const timeFormatter = new Intl.DateTimeFormat("de-DE", {
  hour: "numeric",
  minute: "numeric",
  second: "numeric",
});

// Format the time
const formattedTime = timeFormatter.format(date); // Example output: "14:30:15"
```

In this example, `'de-DE'` represents the German locale.

### Currency localisation

Currency localisation involves formatting currency values to include the appropriate currency symbol, decimal separators, and thousands separators for a specific locale. Here's how you can do it using the `Intl.NumberFormat` object

```js
const currencyValue = 12345.67;

// Create a currency formatter for a specific locale
const currencyFormatter = new Intl.NumberFormat("ja-JP", {
  style: "currency",
  currency: "JPY", // Currency code
});

// Format the currency
const formattedCurrency = currencyFormatter.format(currencyValue); // Example output: "¥12,345.67"
```

In this example, `'ja-JP'` represents the Japanese locale, and 'JPY' is the currency code for Japanese Yen.

See you in the next lesson.
