# Standalone CLI : TailwindCss

## Required dependencies

### Get the executable from the official repository

- **tailwindcss executable** : A utility-first CSS framework for rapidly building custom user interfaces.

[TailwindCss client](https://github.com/tailwindlabs/tailwindcss/releases "Official releases").

```sh
$ mkdir landing-page && cd landing-page
$ curl -sLO https://github.com/tailwindlabs/tailwindcss/releases/latest/download/tailwindcss-linux-x64
$ chmod +x tailwindcss-linux-x64
```

### Folder structure at the end
```
landing-page
├── tailwindcss-linux-x64
├── tailwind.config.js
├── src
│   ├── index.html
│   └── tailwind.css
└── dist
    └── styles.css
```

### Generate the file tailwind.config.js

```sh
# Create a tailwind.config.js file
$ ./tailwindcss-linux-x64 init
```

The tailwind.config.js should appear then copy and paste the following into it :

```js
module.exports = {
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
}
``` 
### Create index.html and tailwind.css files in src folder

1. Copy the following in to /src/index.html
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link href="/dist/styles.css" rel="stylesheet" />
  </head>
  <body>
    <h1 class="text-3xl font-bold underline text-blue-600 bg-slate-400">Hello world!</h1>
  </body>
</html>
```

2. Copy the following into /src/tailwind.css
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

### Start the watcher

```sh
$ ./tailwindcss-linux-x64 -i ./src/tailwind.css -o ./dist/styles.css --watch
```

The watch helps you to debug in real time the css of your html page

### Compile and minify your CSS for production

```sh
$ ./tailwindcss-linux-x64 -i ./src/tailwind.css -o ./dist/styles.css --minify
```
