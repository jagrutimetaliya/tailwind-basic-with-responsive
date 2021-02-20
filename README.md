# Setting Up Tailwind CSS

## 1. Using Tailwind via CDN

Before using the CDN build, please note that many of the features that make Tailwind CSS great are not available without incorporating Tailwind into your build process.

```
 <link href="https://unpkg.com/tailwindcss@^2/dist/tailwind.min.css" rel="stylesheet">
```

=> You can't customize Tailwind's default theme

=> You can't use any `directives` like `@apply`, `@variants`, etc.

=> You can't enable additional variants like `group-focus`

=> You can't install third-party plugins

=> You can't tree-shake unused styles

### Example 

```
<html class="en">
<head>
    <meta charset="UTF-8"/>
    <meta name="viewport" content="width-device-width, initial-scale=1.0" /> 
    <title> Tailwind CSS Demo </title>
    <link href="https://unpkg.com/tailwindcss@^2/dist/tailwind.min.css" rel="stylesheet">

</head>
<body>
    <h1 class="text-4x1 font-bold text-center text-blue-500">Jagruti Metaliya</h1>
</body>
</html>
```
> Note : CDN build large compressed, which means that you have ended with the very large file which is not good for the production. Sites that follow our best practices are almost always under 10kb compressed.

## 2. Generating our own version of tailwind css cli


#### Step 1 : Create a CSS file if you don't have, I have already have my CSS file at css/styles.css 

#### Step 2 : Now use the `@tailwind` directive to inject Tailwind's `base`, `components`, and `utilities` styles. 

simply just copy and paste bellow lines to your css file.

```
/* ./css/styles.css */
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Tailwind will swap these directives out at build-time with all of the styles it generates based on your configured design system.

#### Step 3 : Run the file through PostCSS we can you the tailwindcss-cli to do just that
 ` npx tailwindcss-cli build ./css/styles.css -o ./build/tailwind.css `

here `./css/styles.css` is the input file and `./build/tailwind.css` is output files 

```
<html class="en">
<head>
    <meta charset="UTF-8"/>
    <meta name="viewport" content="width-device-width, initial-scale=1.0" /> 
    <title> Tailwind CSS Demo </title>
    <link href="/css/styles.css" rel="stylesheet">

</head>
<body>
    <h1 class="text-4x1 font-bold text-center text-blue-500">Jagruti Metaliya</h1>
</body>
</html>
```

> Note : Problem with this is we have to build with every change

## 3 : Installing Tailwind CSS as a PostCSS plugin

### Install Tailwind via npm

```
npm init -y
npm install -D tailwindcss postcss autoprefixer vite
```
 add `"dev": "vite"` to your package.json scripts sections, now it will be something like: 
 
 ```
{
  "name": "tailwind",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "dev": "vite"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "autoprefixer": "^10.2.4",
    "postcss": "^8.2.6",
    "tailwindcss": "^2.0.3",
    "vite": "^2.0.1"
  }
}
```

> Note : we are setup our frontend tooling with vite, we have created dev script that runs in a vite server

```
 npx tailwindcss init -p // -p for the  PostCSS 
```
It will create minimal  tailwind and PostCSS config file in your root directory 

now we can remove our build directory also, Now let start the development server using npm  

` npm run dev `


##### Yahh !! we now setup the configuration we are ready to go. 




