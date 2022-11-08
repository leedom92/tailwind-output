# tailwind-output

> We can output the css from `tailwindcss` that we have used.
> 
> The simplest and fastest way to get up and running with Tailwind CSS from scratch is with the Tailwind CLI tool. (The way is from [tailwindcss's document](https://tailwindcss.com/docs/installation))

## 1. Install Tailwind CSS
Install `tailwindcss` via npm, and create your `tailwind.config.js` file.

```sh
npm install -D tailwindcss
npx tailwindcss init
```

## 2. Configure your template paths
Add the paths to all of your template files in your `tailwind.config.js` file.

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

## 3. Add the Tailwind directives to your CSS
Add the `@tailwind` directives for each of Tailwind’s layers to your main CSS file.

```css
/* src/input.css */
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## 4. Start the Tailwind CLI build process
Run the CLI tool to scan your template files for classes and build your CSS.

```sh
npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch
```

## 5. Start using Tailwind in your HTML
Add your compiled CSS file to the `<head>` and start using Tailwind’s utility classes to style your content.

```html
<!-- src/index.html -->
<!doctype html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="/dist/output.css" rel="stylesheet">
</head>
<body>
  <h1 class="text-3xl font-bold underline">
    Hello world!
  </h1>
</body>
</html>
```

> When we use some css from tailwindcss, the output.css will be added automatically.